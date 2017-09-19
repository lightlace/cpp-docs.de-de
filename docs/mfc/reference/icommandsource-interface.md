---
title: ICommandSource-Schnittstelle | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- ICommandSource interface
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: f923a8a42327cb74ce9323f72aae90c7411da27c
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="icommandsource-interface"></a>ICommandSource-Schnittstelle
Verwaltet die Befehle, die von einem Befehlsquellobjekt zu einem Benutzersteuerelement gesendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
interface class ICommandSource  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ICommandSource::AddCommandHandler](#addcommandhandler)|Fügt einen Befehlshandler zu einem Befehlsobjekt für die Quelle an.|  
|[ICommandSource::AddCommandRangeHandler](#addcommandrangehandler)|Ein Befehlsquellobjekt wird eine Gruppe von Befehlshandler hinzugefügt.|  
|[ICommandSource::AddCommandRangeUIHandler](#addcommandrangeuihandler)|Ein Befehlsquellobjekt hinzugefügt eine Gruppe von Benutzer-Schnittstelle Befehl Meldungshandler.|  
|[ICommandSource::AddCommandUIHandler](#addcommandrangeuihandler)|Ein Befehlsquellobjekt hinzugefügt einen Benutzer Schnittstelle Befehl Message-Handler.|  
|[ICommandSource::PostCommand](#postcommand)|Sendet eine Nachricht ohne zu warten, bis sie verarbeitet werden.|  
|[ICommandSource::RemoveCommandHandler](#removecommandhandler)|Entfernt einen Befehlshandler von einem Befehl-Quellobjekt.|  
|[ICommandSource::RemoveCommandRangeHandler](#removecommandrangehandler)|Entfernt eine Gruppe von Befehlshandler von einem Befehl-Quellobjekt.|  
|[ICommandSource::RemoveCommandRangeUIHandler](#removecommandrangeuihandler)|Entfernt eine Gruppe von Benutzer Schnittstelle Befehlshandler Nachricht von einem Befehl-Quellobjekt.|  
|[ICommandSource::RemoveCommandUIHandler](#removecommandrangeuihandler)|Entfernt einen Benutzer Schnittstelle Befehlshandler Nachricht von einem Befehl-Quellobjekt.|  
|[ICommandSource::SendCommand](#sendcommand)|Sendet eine Nachricht und wartet vor der Rückgabe verarbeitet werden.|  
  
### <a name="remarks"></a>Hinweise  
 Beim Hosten eines Benutzersteuerelements in MFC-Ansicht, [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md) Routen Befehle und Update-Befehl UI-Nachrichten auf das Benutzersteuerelement, damit Sie die MFC-Befehle (z. B. Frame Menüelemente und Symbolleisten-Schaltflächen) verarbeiten kann. Durch die Implementierung [ICommandTarget Schnittstelle](../../mfc/reference/icommandtarget-interface.md), geben Sie dem Benutzersteuerelement einen Verweis auf die `ICommandSource` Objekt.  
  
 Finden Sie unter [Gewusst wie: Hinzufügen Befehlsrouting zum Windows Forms-Steuerelements](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zum Verwenden von `ICommandTarget`.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [mithilfe eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxwinforms.h (definiert in der Assembly atlmfc\lib\mfcmifc80.dll)  
  
## <a name="addcommandhandler"></a>ICommandSource::AddCommandHandler
Fügt einen Befehlshandler zu einem Befehlsobjekt für die Quelle an.
```
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Parameter  
`cmdID`  
Die Befehls-ID.  
`cmdHandler`  
Ein Handle für die Handlermethode Befehl.

### <a name="remarks"></a>Hinweise
Diese Methode fügt der Befehl Handler CmdHandler auf das Befehlsquellobjekt und CmdID den Ereignishandler zugeordnet.
Finden Sie unter [Gewusst wie: Hinzufügen Befehlsrouting zum Windows Forms-Steuerelements](https://msdn.microsoft.com/library/y33d8624.aspx) ein Beispiel zur Verwendung von AddCommandHandler.

## <a name="addcommandrangehandler"></a>ICommandSource::AddCommandRangeHandler

Ein Befehlsquellobjekt wird eine Gruppe von Befehlshandler hinzugefügt.
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
Ein Handle für den Message-Handler-Methode, die die Befehle zugeordnet sind.
### <a name="remarks"></a>Hinweise
Diese Methode ordnet einen zusammenhängenden Bereich von Befehls-IDs einem einzelnen Meldungshandler und das Befehlsquellobjekt hinzugefügt. Dies wird für die Behandlung einer Gruppenstatus von verwandten Schaltflächen mit einer Methode verwendet.

## <a name="addcommandrangeuihandler"></a>ICommandSource::AddCommandRangeUIHandler
Ein Befehlsquellobjekt hinzugefügt eine Gruppe von Benutzer-Schnittstelle Befehl Meldungshandler.
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
Ein Handle für den Message-Handler-Methode, die die Befehle zugeordnet sind.

### <a name="remarks"></a>Hinweise
Diese Methode ordnet einen zusammenhängenden Bereich von Befehls-IDs einen einzelnen Benutzer Schnittstelle Befehl Message-Handler und das Befehlsquellobjekt hinzugefügt. Dies wird für die Behandlung einer Gruppenstatus von verwandten Schaltflächen mit einer Methode verwendet.

## <a name="addcommanduihandler"></a>ICommandSource::AddCommandUIHandler
Ein Befehlsquellobjekt hinzugefügt einen Benutzer Schnittstelle Befehl Message-Handler.
```
void AddCommandUIHandler(
    unsigned int cmdID, 
    CommandUIHandler^ cmdUIHandler);
```
### <a name="parameters"></a>Parameter
`cmdID`  
Die Befehls-ID.  
`cmdUIHandler`  
Ein Handle für den Benutzer Schnittstelle Befehl Message-Handler-Methode.

### <a name="remarks"></a>Hinweise
Diese Methode fügt den Benutzer Schnittstelle Befehl Message-Handler CmdHandler auf das Befehlsquellobjekt und CmdID den Ereignishandler zugeordnet.

## <a name="postcommand"></a>ICommandSource::PostCommand
Sendet eine Nachricht ohne zu warten, bis sie verarbeitet werden.
```
void PostCommand(unsigned int command);
```
### <a name="parameters"></a>Parameter
`command`  
Die Befehls-ID der Nachricht bereitgestellt wird.
### <a name="remarks"></a>Hinweise
Diese Methode sendet asynchron die Nachricht, die vom Befehl angegebene ID zugeordnet. CWnd::PostMessage, um die Nachricht in das Fenster Warteschlange gestellt wird und Sie dann ohne zu warten, für das entsprechende Fenster zum Verarbeiten der Nachricht zurück.


## <a name="removecommandhandler"></a>ICommandSource::RemoveCommandHandler
Entfernt einen Befehlshandler von einem Befehl-Quellobjekt.
```
void RemoveCommandHandler(unsigned int cmdID);
```
### <a name="parameters"></a>Parameter
`cmdID`  
Die Befehls-ID.
### <a name="remarks"></a>Hinweise
Diese Methode entfernt die Befehlshandler CmdID aus das Befehlsquellobjekt zugeordnet.


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
Diese Methode entfernt eine Gruppe von Message-Handler die angegebene Befehls-IDs von CmdIDMin und CmdIDMax, aus das Befehlsquellobjekt zugeordnet.

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
Diese Methode entfernt eine Gruppe von Benutzer-Schnittstelle Befehl Meldungshandler, Befehls-IDs zurück durch CmdIDMin und CmdIDMax, aus dem Befehlsquellobjekt zugeordnet.

## <a name="removecommanduihandler"></a>ICommandSource::RemoveCommandUIHandler 
Entfernt einen Benutzer Schnittstelle Befehlshandler Nachricht von einem Befehl-Quellobjekt.
```
void RemoveCommandUIHandler(unsigned int cmdID);
```
### <a name="parameters"></a>Parameter
`cmdID`  
Die Befehls-ID.
### <a name="remarks"></a>Hinweise
Diese Methode entfernt den Benutzer Schnittstelle Nachricht Befehlshandler CmdID aus das Befehlsquellobjekt zugeordnet.

## <a name="sendcommand"></a>ICommandSource::SendCommand 
Sendet eine Nachricht und wartet vor der Rückgabe verarbeitet werden.
```
void SendCommand(unsigned int command);
```
### <a name="parameters"></a>Parameter
`command`  
Die Befehls-ID der Nachricht gesendet werden.
### <a name="remarks"></a>Hinweise
Diese Methode sendet synchron die Nachricht, die vom Befehl angegebene ID zugeordnet. Ruft Funktion CWnd:: SendMessage, um die Nachricht in das Fenster Warteschlange gestellt und wartet, bis diese Fensterprozedur die Nachricht vor der Rückgabe verarbeitet hat.
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Hinzufügen von Befehl Befehlsrouting zum Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [ICommandTarget-Schnittstelle](../../mfc/reference/icommandtarget-interface.md)

