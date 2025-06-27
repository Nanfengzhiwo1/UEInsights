# EnterWorldforPIE(to be continue...)
![image](https://github.com/user-attachments/assets/776783bc-bd57-42cf-8752-abbff098335b)

## DuplicatedWorldForPIE
  _when click the PLay Button,editor will do this action first._
  
```
UWorld* UWorld::GetDuplicatedWorldForPIE(UWorld* InWorld, UPackage* InPIEackage, int32 PIEInstanceID)
{
	TRACE_CPUPROFILER_EVENT_SCOPE(UWorld::GetDuplicatedWorldForPIE);

	check(PIEInstanceID != INDEX_NONE);

	UPackage* InPackage = InWorld->GetOutermost();
	
	FObjectDuplicationParameters Parameters(InWorld, InPIEackage);
	Parameters.DestName = InWorld->GetFName();
	Parameters.DestClass = InWorld->GetClass();
	Parameters.DuplicateMode = EDuplicateMode::PIE;
	Parameters.PortFlags = PPF_DuplicateForPIE;

	UWorld* DuplicatedWorld = CastChecked<UWorld>(StaticDuplicateObjectEx(Parameters));

	DuplicatedWorld->StreamingLevelsPrefix = UWorld::BuildPIEPackagePrefix(PIEInstanceID);

	return DuplicatedWorld;
}
```
### DuplicateObjects
### AddStreamingLevelsPrefix
