---
title: ICommandSource Schnittstelle | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandSource
- AFXWINFORMS/ICommandSource
- AFXWINFORMS/ICommandSource::AddCommandHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::AddCommandUIHandler
- AFXWINFORMS/ICommandSource::PostCommand
- AFXWINFORMS/ICommandSource::RemoveCommandHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::RemoveCommandUIHandler
- AFXWINFORMS/ICommandSource::SendCommand
dev_langs: C++
helpviewer_keywords: ICommandSource interface [MFC]
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dc8ad34ccce059caca8e86a014622e29c14022ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="icommandsource-interface"></a>ICommandSource-Schnittstelle
Verwaltet die Befehle, die von einem Befehlsquellobjekt in einem Benutzersteuerelement gesendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
interface class ICommandSource  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ICommandSource::AddCommandHandler](#addcommandhandler)|Eine Befehlsquellobjekt hinzugefügt Befehlshandler.|  
|[ICommandSource::AddCommandRangeHandler](#addcommandrangehandler)|Ein Befehl Quellobjekt, das hinzugefügt eine Gruppe von Befehlshandler.|  
|[ICommandSource::AddCommandRangeUIHandler](#addcommandrangeuihandler)|Ein Befehl Quellobjekt, das hinzugefügt eine Gruppe von Benutzer Schnittstelle Befehlshandler Nachricht.|  
|[ICommandSource::AddCommandUIHandler](#addcommandrangeuihandler)|Ein Befehlsobjekt für die Quelle hinzugefügt einen Benutzer-Schnittstelle Befehlshandler Nachricht.|  
|[ICommandSource::PostCommand](#postcommand)|Sendet eine Meldung ohne zu warten, bis sie verarbeitet werden.|  
|[ICommandSource::RemoveCommandHandler](#removecommandhandler)|Entfernt einen Befehlshandler von einem Befehl-Quellobjekt.|  
|[ICommandSource::RemoveCommandRangeHandler](#removecommandrangehandler)|Entfernt eine Gruppe von Befehlshandler von einem Befehl-Quellobjekt.|  
|[ICommandSource::RemoveCommandRangeUIHandler](#removecommandrangeuihandler)|Entfernt eine Gruppe von Benutzer Schnittstelle Befehlshandler Nachricht von einem Befehl-Quellobjekt.|  
|[ICommandSource::RemoveCommandUIHandler](#removecommandrangeuihandler)|Entfernt einen Benutzer Schnittstelle Befehlshandler Nachricht von einem Befehl-Quellobjekt.|  
|[ICommandSource::SendCommand](#sendcommand)|Sendet eine Nachricht und wartet, bis er vor der Rückgabe verarbeitet werden.|  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein benutzerdefiniertes Steuerelement in einer MFC-Ansicht hosten [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md) Routen Befehle und Update-Befehl UI Nachrichten auf das Benutzersteuerelement, damit Sie die MFC-Befehle (z. B. Frame Menüelemente und Symbolleisten-Schaltflächen) verarbeiten kann. Durch die Implementierung [ICommandTarget Schnittstelle](../../mfc/reference/icommandtarget-interface.md), Sie geben dem Benutzersteuerelement einen Verweis auf die `ICommandSource` Objekt.  
  
 Finden Sie unter [wie: Hinzufügen Befehlsrouting zum Windows Forms-Steuerelements](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zum Verwenden von `ICommandTarget`.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxwinforms.h (definiert in der Assembly atlmfc\lib\mfcmifc80.dll)  
  
## <a name="addcommandhandler"></a>ICommandSource::AddCommandHandler
Eine Befehlsquellobjekt hinzugefügt Befehlshandler.
```
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Parameter  
`cmdID`  
Die Befehls-ID.  
`cmdHandler`  
Ein Handle für die Handlermethode.

### <a name="remarks"></a>Hinweise
Diese Methode das Befehlsquellobjekt der Befehl Handler CmdHandler hinzugefügt und ist den Handler CmdID zugeordnet.
Finden Sie unter [wie: Hinzufügen Befehlsrouting zum Windows Forms-Steuerelements](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zum AddCommandHandler verwenden.

## <a name="addcommandrangehandler"></a>ICommandSource::AddCommandRangeHandler

Ein Befehl Quellobjekt, das hinzugefügt eine Gruppe von Befehlshandler.
```
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```
### <a name="parameters"></a>Parameter  
`cmdIDMin`  
Der Anfangsindex der Befehls-ID-Bereich.
`cmdIDMax`  
Der Endindex der Befehls-ID-Bereich.
`cmdHandler`  
Ein Handle für die Message-Handler-Methode, die die Befehle zugeordnet sind.
### <a name="remarks"></a>Hinweise
Diese Methode ordnet einen zusammenhängenden Bereich von Befehls-IDs an einen einzelnen Meldungshandler und das Befehlsquellobjekt hinzugefügt. Dies wird verwendet, für die Behandlung einer Gruppenstatus von verwandten Schaltflächen mit einer Methode.

## <a name="addcommandrangeuihandler"></a>ICommandSource::AddCommandRangeUIHandler
Ein Befehl Quellobjekt, das hinzugefügt eine Gruppe von Benutzer Schnittstelle Befehlshandler Nachricht.
```
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin, 
    unsigned int cmdIDMax, 
    CommandUIHandler^ cmdUIHandler);
```
### <a name="parameters"></a>Parameter  
`cmdIDMin`  
Der Anfangsindex der Befehls-ID-Bereich.
`cmdIDMax`  
Der Endindex der Befehls-ID-Bereich.
`cmdHandler`  
Ein Handle für die Message-Handler-Methode, die die Befehle zugeordnet sind.

### <a name="remarks"></a>Hinweise
Diese Methode ordnet einen zusammenhängenden Bereich von Befehls-IDs an einen einzelnen Benutzer Schnittstelle Befehl-Meldungshandler und das Befehlsquellobjekt hinzugefügt. Dies wird verwendet, für die Behandlung einer Gruppenstatus von verwandten Schaltflächen mit einer Methode.

## <a name="addcommanduihandler"></a>ICommandSource::AddCommandUIHandler
Ein Befehlsobjekt für die Quelle hinzugefügt einen Benutzer-Schnittstelle Befehlshandler Nachricht.
```
void AddCommandUIHandler(
    unsigned int cmdID, 
    CommandUIHandler^ cmdUIHandler);
```
### <a name="parameters"></a>Parameter
`cmdID`  
Die Befehls-ID.  
`cmdUIHandler`  
Ein Handle für die Benutzer-Schnittstelle Befehl Message-Handler-Methode.

### <a name="remarks"></a>Hinweise
Diese Methode das Befehlsquellobjekt Benutzer Schnittstelle Befehl Message-Handler-CmdHandler hinzugefügt und ist den Handler CmdID zugeordnet.

## <a name="postcommand"></a>ICommandSource::PostCommand
Sendet eine Meldung ohne zu warten, bis sie verarbeitet werden.
```
void PostCommand(unsigned int command);
```
### <a name="parameters"></a>Parameter
`command`  
Die Befehls-ID der Nachricht gesendet werden.
### <a name="remarks"></a>Hinweise
Diese Methode sendet asynchron die Nachricht, die vom Befehl angegebene ID zugeordnet ist. Er ruft CWnd::PostMessage, um die Nachricht in das Fenster Nachrichtenwarteschlange zu platzieren und dann ohne zu warten, für das entsprechende Fenster zum Verarbeiten der Nachricht zurückgegeben.


## <a name="removecommandhandler"></a>ICommandSource::RemoveCommandHandler
Entfernt einen Befehlshandler von einem Befehl-Quellobjekt.
```
void RemoveCommandHandler(unsigned int cmdID);
```
### <a name="parameters"></a>Parameter
`cmdID`  
Die Befehls-ID.
### <a name="remarks"></a>Hinweise
Diese Methode entfernt die Befehlshandler CmdID aus dem Befehlsquellobjekt zugeordnet.


## <a name="removecommandrangecommandhandler"></a>ICommandSource::RemoveCommandRangeHandler 
Entfernt eine Gruppe von Befehlshandler von einem Befehl-Quellobjekt.
```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```
### <a name="parameters"></a>Parameter
`cmdIDMin`  
Der Anfangsindex der Befehls-ID-Bereich.
`cmdIDMax`  
Der Endindex der Befehls-ID-Bereich.
### <a name="remarks"></a>Hinweise
Diese Methode entfernt eine Gruppe von-Meldungshandler die Befehls-IDs angegeben durch CmdIDMin und CmdIDMax, aus dem Befehlsquellobjekt zugeordnet.

## <a name="removecommandrangeuihandler"></a>ICommandSource::RemoveCommandRangeUIHandler 
Entfernt eine Gruppe von Benutzer Schnittstelle Befehlshandler Nachricht von einem Befehl-Quellobjekt.
```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```
### <a name="parameters"></a>Parameter
`cmdIDMin`  
Der Anfangsindex der Befehls-ID-Bereich.
`cmdIDMax`  
Der Endindex der Befehls-ID-Bereich.
### <a name="remarks"></a>Hinweise
Diese Methode entfernt eine Gruppe von Benutzer-Schnittstelle Befehl Meldungshandler, der Befehls-IDs angegeben durch CmdIDMin und CmdIDMax, aus dem Befehlsquellobjekt zugeordnet.

## <a name="removecommanduihandler"></a>ICommandSource::RemoveCommandUIHandler 
Entfernt einen Benutzer Schnittstelle Befehlshandler Nachricht von einem Befehl-Quellobjekt.
```
void RemoveCommandUIHandler(unsigned int cmdID);
```
### <a name="parameters"></a>Parameter
`cmdID`  
Die Befehls-ID.
### <a name="remarks"></a>Hinweise
Diese Methode entfernt Benutzer Schnittstelle Nachricht Befehlshandler CmdID aus dem Befehlsquellobjekt zugeordnet.

## <a name="sendcommand"></a>ICommandSource::SendCommand 
Sendet eine Nachricht und wartet, bis er vor der Rückgabe verarbeitet werden.
```
void SendCommand(unsigned int command);
```
### <a name="parameters"></a>Parameter
`command`  
Die Befehls-ID der Nachricht gesendet werden.
### <a name="remarks"></a>Hinweise
Diese Methode sendet synchron die Nachricht, die vom Befehl angegebene ID zugeordnet ist. Ruft die Funktion CWnd:: SendMessage, um die Nachricht in das Fenster Nachrichtenwarteschlange einstellt auf und wartet, bis diese Fensterprozedur die Nachricht vor der Rückgabe verarbeitet hat.
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Hinzufügen (Befehl) Befehlsrouting zum Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [ICommandTarget-Schnittstelle](../../mfc/reference/icommandtarget-interface.md)
