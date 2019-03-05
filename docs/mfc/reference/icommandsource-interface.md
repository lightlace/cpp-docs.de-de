---
title: ICommandSource-Schnittstelle
ms.date: 11/04/2016
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
helpviewer_keywords:
- ICommandSource interface [MFC]
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
ms.openlocfilehash: 21c4f4544a6ccf2342580bc5859739fc1f50d0c2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296019"
---
# <a name="icommandsource-interface"></a>ICommandSource-Schnittstelle

Verwaltet die Befehle, die von einem Quellobjekt für den Befehl zu einem Benutzersteuerelement gesendet.

## <a name="syntax"></a>Syntax

```
interface class ICommandSource
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[ICommandSource::AddCommandHandler](#addcommandhandler)|Ein Befehlsobjekt für die Datenquelle wird einen Befehlshandler hinzugefügt.|
|[ICommandSource::AddCommandRangeHandler](#addcommandrangehandler)|Ein Befehlsobjekt für die Quelle wird eine Gruppe von Befehlshandler hinzugefügt.|
|[ICommandSource::AddCommandRangeUIHandler](#addcommandrangeuihandler)|Ein Befehlsobjekt für die Quelle wird eine Gruppe von Benutzer-Schnittstelle Nachricht Befehlshandler hinzugefügt.|
|[ICommandSource::AddCommandUIHandler](#addcommandrangeuihandler)|Ein Befehlsobjekt für die Quelle wird einen Benutzer Schnittstelle Befehlshandler Meldung hinzugefügt.|
|[ICommandSource::PostCommand](#postcommand)|Sendet eine Nachricht ohne zu warten, bis es verarbeitet werden.|
|[ICommandSource::RemoveCommandHandler](#removecommandhandler)|Entfernt einen Befehlshandler von einem Befehl-Quellobjekt.|
|[ICommandSource::RemoveCommandRangeHandler](#removecommandrangehandler)|Entfernt eine Gruppe von Befehlshandler von einem Befehl-Quellobjekt.|
|[ICommandSource::RemoveCommandRangeUIHandler](#removecommandrangeuihandler)|Entfernt eine Gruppe von Benutzer Schnittstelle Befehlshandler-Nachricht von einem Befehl-Quellobjekt.|
|[ICommandSource::RemoveCommandUIHandler](#removecommandrangeuihandler)|Entfernt einen Benutzer Schnittstelle Befehlshandler Nachricht von einem Quellobjekt für den Befehl.|
|[ICommandSource::SendCommand](#sendcommand)|Sendet eine Nachricht und wartet darauf, dass sie vor der Rückgabe verarbeitet werden.|

### <a name="remarks"></a>Hinweise

Beim Hosten eines Benutzersteuerelements in MFC-Ansicht, [CWinFormsView-Klasse](../../mfc/reference/cwinformsview-class.md) Routen Befehle und Update-Befehl UI-Nachrichten an das Steuerelement, damit Sie die MFC-Befehle (z. B. Frame Menüelemente und Symbolleistenschaltflächen) verarbeiten kann. Durch die Implementierung [ICommandTarget-Schnittstelle](../../mfc/reference/icommandtarget-interface.md), geben Sie dem Benutzersteuerelement einen Verweis auf die `ICommandSource` Objekt.

Weitere Informationen finden Sie unter [How to: Hinzufügen von Befehlsrouting an der Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zur Verwendung für `ICommandTarget`.

Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [verwenden ein Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Anforderungen

**Header:** afxwinforms.h (definiert in der Assembly atlmfc\lib\mfcmifc80.dll)

## <a name="addcommandhandler"></a>  ICommandSource::AddCommandHandler

Ein Befehlsobjekt für die Datenquelle wird einen Befehlshandler hinzugefügt.
```
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Parameter

*cmdID*<br/>
Die Befehls-ID.
*cmdHandler*<br/>
Ein Handle für die Handlermethode.

### <a name="remarks"></a>Hinweise

Diese Methode fügt den Befehl Handler CmdHandler auf das Befehlsquellobjekt und CmdID wird den Handler zugeordnet.
Weitere Informationen finden Sie unter [How to: Hinzufügen von Befehlsrouting an der Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zur Verwendung von AddCommandHandler.

## <a name="addcommandrangehandler"></a> ICommandSource::AddCommandRangeHandler

Ein Befehlsobjekt für die Quelle wird eine Gruppe von Befehlshandler hinzugefügt.
```
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Parameter

*cmdIDMin*<br/>
Der Startindex des der Befehls-ID-Bereich.
*cmdIDMax*<br/>
Der Endindex der Befehls-ID-Bereich.
*cmdHandler*<br/>
Ein Handle für die Message-Handler-Methode, die die Befehle zugeordnet sind.
### <a name="remarks"></a>Hinweise

Diese Methode ordnet einen zusammenhängenden Bereich von Befehls-IDs ein einzelnes Message-Handler und das Befehlsquellobjekt hinzugefügt. Hiermit wird für die Verarbeitung einer Gruppenstatus von zugehörigen Schaltflächen mit einer Methode.

## <a name="addcommandrangeuihandler"></a> ICommandSource::AddCommandRangeUIHandler

Ein Befehlsobjekt für die Quelle wird eine Gruppe von Benutzer-Schnittstelle Nachricht Befehlshandler hinzugefügt.
```
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Parameter

*cmdIDMin*<br/>
Der Startindex des der Befehls-ID-Bereich.
*cmdIDMax*<br/>
Der Endindex der Befehls-ID-Bereich.
*cmdHandler*<br/>
Ein Handle für die Message-Handler-Methode, die die Befehle zugeordnet sind.

### <a name="remarks"></a>Hinweise

Diese Methode ordnet einen zusammenhängenden Bereich von Befehls-IDs einen einzelnen Benutzer Schnittstelle Befehl Message-Handler und das Befehlsquellobjekt hinzugefügt. Hiermit wird für die Verarbeitung einer Gruppenstatus von zugehörigen Schaltflächen mit einer Methode.

## <a name="addcommanduihandler"></a> ICommandSource::AddCommandUIHandler

Ein Befehlsobjekt für die Quelle wird einen Benutzer Schnittstelle Befehlshandler Meldung hinzugefügt.
```
void AddCommandUIHandler(
    unsigned int cmdID,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Parameter

*cmdID*<br/>
Die Befehls-ID.
*cmdUIHandler*<br/>
Ein Handle für die Benutzer-Schnittstelle Befehl Message-Handler-Methode.

### <a name="remarks"></a>Hinweise

Diese Methode fügt den Benutzer-Schnittstelle Befehl Message-Handler CmdHandler auf das Befehlsquellobjekt und CmdID wird den Handler zugeordnet.

## <a name="postcommand"></a> ICommandSource::PostCommand

Sendet eine Nachricht ohne zu warten, bis es verarbeitet werden.
```
void PostCommand(unsigned int command);
```

### <a name="parameters"></a>Parameter

*command*<br/>
Die Befehls-ID der Nachricht, die gepostet werden soll.
### <a name="remarks"></a>Hinweise

Diese Methode sendet asynchron die Nachricht, die vom Befehl angegebene ID zugeordnet. Ruft die CWnd::PostMessage, um die Nachricht in der Nachrichtenwarteschlange des Fensters zu platzieren und gibt dann zurück, ohne zu warten, für das entsprechende Fenster zur Verarbeitung der Nachricht.

## <a name="removecommandhandler"></a> ICommandSource::RemoveCommandHandler

Entfernt einen Befehlshandler von einem Befehl-Quellobjekt.
```
void RemoveCommandHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Parameter

*cmdID*<br/>
Die Befehls-ID.
### <a name="remarks"></a>Hinweise

Diese Methode entfernt den Befehlshandler, der aus das Befehlsquellobjekt CmdID zugeordnet.

## <a name="removecommandrangecommandhandler"></a> ICommandSource::RemoveCommandRangeHandler

Entfernt eine Gruppe von Befehlshandler von einem Befehl-Quellobjekt.
```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Parameter

*cmdIDMin*<br/>
Der Startindex des der Befehls-ID-Bereich.
*cmdIDMax*<br/>
Der Endindex der Befehls-ID-Bereich.
### <a name="remarks"></a>Hinweise

Diese Methode entfernt eine Gruppe von Meldungshandler, der angegebenen Befehls-IDs von CmdIDMin und CmdIDMax, aus das Befehlsquellobjekt zugeordnet.

## <a name="removecommandrangeuihandler"></a> ICommandSource::RemoveCommandRangeUIHandler

Entfernt eine Gruppe von Benutzer Schnittstelle Befehlshandler-Nachricht von einem Befehl-Quellobjekt.
```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Parameter

*cmdIDMin*<br/>
Der Startindex des der Befehls-ID-Bereich.
*cmdIDMax*<br/>
Der Endindex der Befehls-ID-Bereich.
### <a name="remarks"></a>Hinweise

Diese Methode entfernt eine Gruppe von Benutzer-Schnittstelle Nachricht Befehlshandler, der angegebenen Befehls-IDs von CmdIDMin und CmdIDMax, aus das Befehlsquellobjekt zugeordnet.

## <a name="removecommanduihandler"></a> ICommandSource::RemoveCommandUIHandler

Entfernt einen Benutzer Schnittstelle Befehlshandler Nachricht von einem Quellobjekt für den Befehl.
```
void RemoveCommandUIHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Parameter

*cmdID*<br/>
Die Befehls-ID.
### <a name="remarks"></a>Hinweise

Diese Methode entfernt den Benutzer Schnittstelle Nachricht Befehlshandler aus das Befehlsquellobjekt CmdID zugeordnet.

## <a name="sendcommand"></a> ICommandSource::SendCommand

Sendet eine Nachricht und wartet darauf, dass sie vor der Rückgabe verarbeitet werden.
```
void SendCommand(unsigned int command);
```

### <a name="parameters"></a>Parameter

*command*<br/>
Die Befehls-ID der Nachricht gesendet werden.
### <a name="remarks"></a>Hinweise

Diese Methode sendet synchron die Nachricht, die vom Befehl angegebene ID zugeordnet. Ruft die Funktion CWnd:: SendMessage, um die Nachricht in der Nachrichtenwarteschlange des Fensters zu platzieren und wartet, bis diese Fensterprozedur die Meldung vor der Rückgabe verarbeitet hat.
## <a name="see-also"></a>Siehe auch

[Vorgehensweise: Hinzufügen von Befehlsrouting zum Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[ICommandTarget-Schnittstelle](../../mfc/reference/icommandtarget-interface.md)
