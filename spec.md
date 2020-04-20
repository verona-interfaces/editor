# Authoring Module interface definition v1.0
IQB/mechtel 11.3.2019
## 1. FromAuthoringModule.ReadyNotification
Unit Authoring Module -> Host

Announcing Load Complete and the version of the interface this Authoring Tool understands; 
the version follows the semver-system so it’s only another major version what is not understood
```
{
    type: 'vo.FromAuthoringModule.ReadyNotification';
	version: number;
}
```

## 2. ToAuthoringModule.DataTransfer
Host -> Unit Authoring Module

Answering 'vo.FromUnitAuthoring.ReadyNotification'
```
{
    type: 'vo.ToAuthoringModule.DataTransfer';
    sessionId: string; 
    unitDefinition: string;
}
```

## 3. FromAuthoringModule.ChangedNotification
Unit Authoring Module -> Host

Sent to announce that unit definition has changed
```
{
    type: 'vo.FromAuthoringModule.ChangedNotification';
    sessionId: string;
}
```

## 4. ToAuthoringModule.DataRequest
Host -> Unit Authoring Module

The host calls to get the (changed) unit definition
```
{
    type: 'vo.ToAuthoringModule.DataRequest';
    sessionId: string;
}
```

## 5. FromAuthoringModule.DataTransfer
Unit Authoring Module -> Host

Direct answer to Vo_ToUnitAuthoring_ChangedDataCall; the unitDefinitionType ensures, that the 
right itemplayer will be chosen to run this unit
```
{
    type: 'vo.FromAuthoringModule.DataTransfer';
    sessionId: string;
    unitDefinition: string;
    player: string;
}
```