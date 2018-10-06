---
title: Message-Zuordnungs-Makros (MFC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFXWIN/DECLARE_MESSAGE_MAP
- AFXWIN/BEGIN_MESSAGE_MAP
- AFXWIN/BEGIN_TEMPLATE_MESSAGE_MAP
- AFXWIN/END_MESSAGE_MAP
- AFXWIN/ON_COMMAND
- AFXWIN/ON_COMMAND_EX
- AFXWIN/ON_CONTROL
- AFXWIN/ON_MESSAGE
- AFXWIN/ON_OLECMD
- AFXWIN/ON_REGISTERED_MESSAGE
- AFXWIN/ON_REGISTERED_THREAD_MESSAGE
- AFXWIN/ON_THREAD_MESSAGE
- AFXWIN/ON_UPDATE_COMMAND_UI
- AFXWIN/ON_COMMAND_RANGE
- AFXWIN/ON_UPDATE_COMMAND_UI_RANGE
- AFXWIN/ON_CONTROL_RANGE
dev_langs:
- C++
helpviewer_keywords:
- message map macros
- Windows messages [MFC], declaration
- demarcating Windows messages
- message maps [MFC], macros
- message maps [MFC], declaration and demarcation
- message mapping macros
- ranges, message map
- message map ranges
ms.assetid: 531b15ce-32b5-4ca0-a849-bb519616c731
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aa5cf1be80b22d3577347dbf7de9ee262125aa86
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2018
ms.locfileid: "48821360"
---
# <a name="message-map-macros-mfc"></a>Meldungszuordnungsmakros (MFC)

Um meldungszuordnungen zu unterstützen, stellt MFC die folgenden Makros:

### <a name="message-map-declaration-and-demarcation-macros"></a>Meldungszuordnung Deklaration und Demarkation-Makros

|||
|-|-|
|[DECLARE_MESSAGE_MAP](#declare_message_map)|Deklariert, dass eine meldungszuordnung in einer Klasse verwendet wird, Nachrichten Funktionen zuzuordnen (muss in der Klassendeklaration verwendet werden).|
|[BEGIN_MESSAGE_MAP](#begin_message_map)|Beginn der Definition einer meldungszuordnung (muss in der klassenimplementierung verwendet werden).|
|[BEGIN_TEMPLATE_MESSAGE_MAP](#begin_template_interface_map)|Beginn der Definition einer meldungszuordnung für einen Klassentyp mit einem einzelnen Vorlagenargument an. |
|[END_MESSAGE_MAP](#end_message_map)|Beendet die Definition einer meldungszuordnung (muss in der klassenimplementierung verwendet werden).|

### <a name="message-mapping-macros"></a>Nachrichtenzuordnung Makros

|||
|-|-|
|[ON_COMMAND](#on_command)|Gibt an, welche Funktion eine angegebenen Nachricht behandelt.|
|[ON_COMMAND_EX](#on_command_ex)|Gibt an, welche Funktion eine angegebenen Nachricht behandelt.|
|[ON_CONTROL](#on_control)|Gibt an, welche Funktion angegebenen Steuerelement-Benachrichtigung behandelt.|
|[ON_MESSAGE](#on_message)|Gibt an, welche Funktion eine benutzerdefinierte Meldung behandelt.|
|[ON_OLECMD](#on_olecmd)|Gibt an, welche Funktion einen Menübefehl aus DocObject oder den Container behandelt.|
|[ON_REGISTERED_MESSAGE](#on_registered_message)|Gibt an, welche Funktion eine registrierte benutzerdefinierten Meldung behandelt.|
|[ON_REGISTERED_THREAD_MESSAGE](#on_registered_thread_message)|Gibt an, welche Funktion bei eine registrierte benutzerdefinierten Meldung behandelt eine `CWinThread` Klasse.|
|[ON_THREAD_MESSAGE](#on_thread_message)|Gibt an, welche Funktion bei eine benutzerdefinierten Meldung behandelt eine `CWinThread` Klasse.|
|[ON_UPDATE_COMMAND_UI](#on_update_command_ui)|Gibt an, welche Funktion eine angegebenen Benutzeroberflächen-Update-Befehlsnachricht behandelt.|

### <a name="message-map-range-macros"></a>Meldungszuordnung Range-Makros

|||
|-|-|
|[ON_COMMAND_RANGE](#on_command_range)|Gibt an, welche Funktion den Bereich der Befehls-IDs angegeben werden, in die ersten beiden Parameter in das Makro behandelt.|
|[ON_UPDATE_COMMAND_UI_RANGE](#on_update_command_ui_range)|Gibt an, welche updatehandler den Bereich der Befehls-IDs, die in der ersten beiden Pa angegebenen behandelt] rameter in das Makro.|
|[ON_CONTROL_RANGE](#on_control_range)|Gibt an, welche Funktion das Behandeln von Benachrichtigungen aus dem Bereich von Steuerelement-IDs, die in der zweiten und dritten Parameter in das Makro angegeben zu werden. Der erste Parameter ist eine Steuerelement-Benachrichtigung, z. B. BN_CLICKED.|

Weitere Informationen auf meldungszuordnungen, die meldungszuordnung Deklaration und demarkation-Makros und die Nachricht-Zuordnungs-Makros finden Sie unter [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md) und [Nachrichtenbehandlung und Zuordnung Themen](../../mfc/message-handling-and-mapping.md). Weitere Informationen zu Meldungszuordnungsbereiche, finden Sie unter [Handler für Meldungszuordnungsbereiche](../../mfc/handlers-for-message-map-ranges.md).

## <a name="begin_message_map"></a> BEGIN_MESSAGE_MAP

Beginn der Definition Ihrer meldungszuordnung.

### <a name="syntax"></a>Syntax

```
BEGIN_MESSAGE_MAP( theClass, baseClass )
```

### <a name="parameters"></a>Parameter

*theClass*<br/>
Gibt an, dass der Name der Klasse, dessen Meldung eine Zuordnung, ist.

*Basisklasse*<br/>
Gibt den Namen der Basisklasse der *TheClass*.

### <a name="remarks"></a>Hinweise

Klicken Sie in der Implementierungsdatei (.cpp), die die Member-Funktionen für die Klasse definiert, starten Sie die meldungszuordnung, mit dem BEGIN_MESSAGE_MAP-Makro, und klicken Sie dann fügen Sie Makroeinträge für jede der Meldungshandler-Funktionen hinzu, und schließen Sie die meldungszuordnung, mit der END_MESSAGE_MAP -Makro.

Weitere Informationen über meldungszuordnungen finden Sie unter [Meldungszuordnungen](message-maps-mfc.md)

### <a name="example"></a>Beispiel

```cpp
BEGIN_MESSAGE_MAP(CMainFrame, CMDIFrameWnd)
   ON_WM_CREATE()
END_MESSAGE_MAP()
```

### <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="begin_template_message_map"></a>BEGIN_TEMPLATE_MESSAGE_MAP

Beginn der Definition einer meldungszuordnung für einen Klassentyp mit einem einzelnen Vorlagenargument an.

### <a name="syntax"></a>Syntax

```
BEGIN_TEMPLATE_MESSAGE_MAP( theClass, type_name, baseClass )
```

### <a name="parameters"></a>Parameter

*theClass*<br/>
Gibt an, dass der Name der Klasse, dessen Meldung eine Zuordnung, ist.

*type_name*<br/>
Der Name des Vorlagenparameters für die Klasse angegeben.

*Basisklasse*<br/>
Gibt den Namen der Basisklasse der *TheClass*.

### <a name="remarks"></a>Hinweise

Dieses Makro ähnelt den [BEGIN_MESSAGE_MAP](message-map-macros-mfc.md#begin_message_map) Makro; dieses Makro ist jedoch für Klassen, die mit einem einzelnen Vorlagenargument vorgesehen.

Starten Sie in der Methode Implementation-Abschnitt der Klasse die meldungszuordnung, mit dem Makro BEGIN_TEMPLATE_MESSAGE_MAP; Fügen Sie Makroeinträge klicken Sie dann für jede Ihrer Meldungshandler-Methoden, wie bei einer Standardnachricht-Zuordnung aus. Mit dem BEGIN_MESSAGE_MAP-Makro, mit die Vorlage-meldungszuordnung Abschließen der [END_MESSAGE_MAP](message-map-macros-mfc.md#end_message_map) Makro.

Weitere Informationen zum Implementieren von meldungszuordnungen für Vorlagenklassen finden Sie unter [Vorgehensweise: Erstellen einer Meldungszuordnung für eine Vorlagenklasse](../how-to-create-a-message-map-for-a-template-class.md).

### <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

## <a name="declare_message_map"></a>  DECLARE_MESSAGE_MAP

Deklariert, dass die Klasse eine meldungszuordnung definiert. Jede `CCmdTarget`-abgeleiteten Klasse in Ihrem Programm muss eine meldungszuordnung, um Nachrichten zu verarbeiten bereitstellen.

### <a name="syntax"></a>Syntax

```
DECLARE_MESSAGE_MAP( )
```

### <a name="remarks"></a>Hinweise

Verwenden Sie das DECLARE_MESSAGE_MAP-Makro, am Ende der Klassendeklaration. Klicken Sie dann in der CPP-Datei, die die Member-Funktionen für die Klasse definiert, verwenden Sie im BEGIN_MESSAGE_MAP-Makro Makroeinträge für jede der Meldungshandler funktioniert und die END_MESSAGE_MAP-Makro.

> [!NOTE]
>  Wenn Sie einen beliebigen Member nach DECLARE_MESSAGE_MAP deklarieren, müssen Sie einen neuen Zugriffstyp angeben (**öffentliche**, **private**, oder **geschützt**) für sie.

Weitere Informationen zu nachrichtenzuordnungen und die DECLARE_MESSAGE_MAP-Makro, finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).

### <a name="example"></a>Beispiel

```cpp
class CMainFrame : public CMDIFrameWnd
{
   DECLARE_MESSAGE_MAP()

   // Remainder of class declaration omitted.
```

### <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

## <a name="end_message_map"></a>  END_MESSAGE_MAP

Beendet die Definition der Zuordnung Nachricht.

### <a name="syntax"></a>Syntax

```
END_MESSAGE_MAP( )
```

### <a name="remarks"></a>Hinweise

Weitere Informationen zu nachrichtenzuordnungen und die END_MESSAGE_MAP-Makro, finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).

### <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

## <a name="on_command"></a>  ON_COMMAND

Dieses Makro wird eine Nachricht auf eine Memberfunktion zugeordnet.

### <a name="syntax"></a>Syntax

```
ON_COMMAND( id, memberFxn )
```

### <a name="parameters"></a>Parameter

*ID*<br/>
Die Befehls-ID.

*memberFxn*<br/>
Der Name der Meldungshandler-Funktion, die der Befehl zugeordnet ist.

### <a name="remarks"></a>Hinweise

Er gibt an, welche Funktion behandelt eine Nachricht aus einem Befehl Benutzeroberflächen-Objekt, z. B. eine Menü oder eine Symbolleisten-Schaltfläche.

Wenn ein Befehlsziel Objekt auf eine Windows-WM_COMMAND-Meldung mit der angegebenen ID empfängt, ruft ON_COMMAND die Memberfunktion `memberFxn` zur Verarbeitung der Nachricht.

Verwenden Sie ON_COMMAND, um einen einzelnen Befehl auf eine Memberfunktion zuzuordnen. Verwendung [ON_COMMAND_RANGE](#on_command_range) , einen Bereich für Befehls-Ids auf eine Memberfunktion zuzuordnen. Nur ein Meldungszuordnungseintrags kann eine angegebenen Befehls-Id überein. Sie können nicht mehr als einen Handler, also einen Befehl zuordnen. Weitere Informationen und Beispiele finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).

### <a name="example"></a>Beispiel

```cpp
BEGIN_MESSAGE_MAP(CMFCListViewDoc, CDocument)
   ON_COMMAND(ID_MYCOMMAND, &CMFCListViewDoc::OnMycommand)
END_MESSAGE_MAP()
```

### <a name="requirements"></a>Anforderungen

**Header:** afxmsg_.h

## <a name="on_command_ex"></a>  ON_COMMAND_EX

Erweiterte Befehlshandler Member-Funktion.

### <a name="syntax"></a>Syntax

```
ON_COMMAND_EX(id, memberFxn);
```

### <a name="parameters"></a>Parameter

*ID*<br/>
Die Befehls-ID.

*memberFxn*<br/>
Der Name der Meldungshandler-Funktion, die der Befehl zugeordnet ist.

### <a name="remarks"></a>Hinweise

Eine erweiterte Form der Nachricht Befehlshandler ist verfügbar für erweiterte verwendet. Die ON_COMMAND_EX-Makro wird für solche Meldungshandler verwendet, und es bietet eine Obermenge der Funktionen [ON_COMMAND] (#On_command).  Erweiterte Befehlshandler Member-Funktionen auf einen einzelnen Parameter, UINT, enthält die Befehls-ID und einen booleschen Wert zurückzugeben. Der Rückgabewert muss wahr sein.

Dieses Makro ordnet eine befehlsmeldung an eine erweiterte Befehlshandler Member-Funktion.

### <a name="syntax"></a>Syntax

```
ON_COMMAND_EX(id,  memberFxn);
```

### <a name="parameters"></a>Parameter

*ID*<br/>
Die Befehls-ID.

*memberFxn*<br/>
Der Name der Meldungshandler-Funktion, die der Befehl zugeordnet ist.

### <a name="remarks"></a>Hinweise

Eine erweiterte Form der Nachricht Befehlshandler ist verfügbar für erweiterte verwendet. Die ON_COMMAND_EX-Makro wird für solche Meldungshandler verwendet, und es bietet eine Obermenge der der [ON_COMMAND](message-map-macros-mfc.md#on_command) Funktionalität. Erweiterte Befehlshandler Member-Funktionen auf einen einzelnen Parameter, UINT, enthält die Befehls-ID und einen booleschen Wert zurückzugeben. Der Rückgabewert muss auf "true", um anzugeben, dass der Befehl behandelt wurde; Andernfalls wird auf anderen Befehl Zielobjekte weiterzuleiten.
Weitere Informationen finden Sie im technischen Hinweis [TN006: Meldungszuordnungen] tm006-Nachricht-maps.md).

### <a name="requirements"></a>Anforderungen

Headerdatei: afxmsg_.h

### <a name="see-also"></a>Siehe auch

[ON_COMMAND](message-map-macros-mfc.md#on_command)<br/>
[TN006: Meldungszuordnungen](../tn006-message-maps.md)

## <a name="on_control"></a>  ON_CONTROL

Gibt an, welche Funktion eine Benachrichtigung für benutzerdefinierte Steuerelemente behandelt.

### <a name="syntax"></a>Syntax

```
ON_CONTROL( wNotifyCode, id, memberFxn )
```

### <a name="parameters"></a>Parameter

*wNotifyCode schalten*<br/>
Der Benachrichtigungscode des Steuerelements.

*ID*<br/>
Die Befehls-ID.

*memberFxn*<br/>
Der Name der Meldungshandler-Funktion, die der Befehl zugeordnet ist.

### <a name="remarks"></a>Hinweise

Benachrichtigungsmeldungen des Registersteuerelements stammen, von einem Steuerelement an das übergeordnete Fenster gesendet.

Es sollte genau eine ON_CONTROL-Makro-Anweisung in der meldungszuordnung für jedes Steuerelement-Benachrichtigung, die auf eine Message-Handler-Funktion zugeordnet werden muss.

Weitere Informationen und Beispiele finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).

### <a name="requirements"></a>Anforderungen

**Header:** afxmsg_.h

## <a name="on_message"></a>  ON_MESSAGE

Gibt an, welche Funktion eine benutzerdefinierte Meldung behandelt.

### <a name="syntax"></a>Syntax

```
ON_MESSAGE( message, memberFxn )
```

### <a name="parameters"></a>Parameter

*message*<br/>
Die Meldungs-ID.

*memberFxn*<br/>
Der Name der Meldungshandler-Funktion, die die Nachricht zugeordnet ist.

Der Typ der Funktion muss `afx_msg LRESULT (CWnd::*)(WPARAM, LPARAM)`.

### <a name="remarks"></a>Hinweise

Benutzerdefinierte Meldungen sind alle Nachrichten, die nicht standardmäßige Windows-WM_MESSAGE Nachrichten sind. Wenn Sie eine Meldungs-ID auswählen zu können, müssen Sie Werte in den Bereich der WM_USER (0 x 0400) zu 0xBFFF 0x7FFF oder WM_APP (0 x 8000) verwenden. Weitere Informationen in Bezug auf die Meldungs-IDs finden Sie unter [WM_APP](/windows/desktop/winmsg/wm-app).

Es sollte genau eine ON_MESSAGE-Makro-Anweisung in der meldungszuordnung für jede benutzerdefinierte Nachricht, die eine Message-Handler-Funktion zugeordnet werden muss.

> [!NOTE]
>  Zusätzlich zu den benutzerdefinierten Nachrichten behandelt ON_MESSAGE weniger gängige Windows-Meldungen. Weitere Informationen finden Sie im Knowledge Base-Artikel [99848: INFO: ON_MESSAGE()-Makro verwenden, um Karte weniger übliche Nachrichten](http://go.microsoft.com/fwlink/p/?linkid=192022).

Weitere Informationen und Beispiele finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md) und [benutzerdefinierte Handler](user-defined-handlers.md)

### <a name="example"></a>Beispiel

```cpp
#define WM_MYMESSAGE (WM_USER + 100)

BEGIN_MESSAGE_MAP(CMyWnd2, CWnd)
   ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)
END_MESSAGE_MAP()

// inside the class declaration
afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

LRESULT CMyWnd2::OnMyMessage(WPARAM wParam, LPARAM lParam)
{
   UNREFERENCED_PARAMETER(wParam);
   UNREFERENCED_PARAMETER(lParam);

   // Handle message here.

   return 0;
}
```

### <a name="requirements"></a>Anforderungen

**Header:** afxmsg_.h

## <a name="on_olecmd"></a>  ON_OLECMD

Leitet Befehle über die Dispatch-Befehlsschnittstelle `IOleCommandTarget`.

### <a name="syntax"></a>Syntax

```
ON_OLECMD( pguid, olecmdid, id )
```

### <a name="parameters"></a>Parameter

*pguid*<br/>
Der Bezeichner der Befehlsgruppe, zu der der Befehl gehört. Verwenden Sie NULL für den "standard"-Gruppe an.

*olecmdid*<br/>
Der Bezeichner der der OLE-Befehl.

*ID*<br/>
Die Menü-ID, Symbolleisten-ID, Schaltflächen-ID oder andere-ID der Ressource oder des Objekts, die Sie den Befehl ausgeben.

### <a name="remarks"></a>Hinweise

`IOleCommandTarget` ermöglicht einen Container, um Befehle zu empfangen, die in DocObjects-Benutzeroberfläche stammen und der Container kann die gleichen Befehle zu senden (z. B. neu "," Open "," SaveAs "und" auf das Menü "Datei"; Drucken, und kopieren, einfügen, rückgängig zu machen, und so weiter auf das Menü "Bearbeiten"), DocObject.

`IOleCommandTarget` ist einfacher als OLE-Automatisierung des `IDispatch`. `IOleCommandTarget` beruht vollständig auf einen Standardsatz von Befehlen, die nur selten haben Argumente aus, und keine Typinformationen beteiligt ist (die typsicherheit wird auch die Befehlsargumente verringert). Wenn Sie benötigen, um Befehle mit Argumenten zu senden, verwenden Sie [COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd).

Die `IOleCommandTarget` standardmäßigen Menübefehle von MFC in der folgenden Makros implementiert wurden:

**ON_OLECMD_CLEARSELECTION)**

Sendet den Befehl zum Löschen bearbeiten. Als implementiert:

`ON_OLECMD(NULL, OLECMDID_CLEARSELECTION, ID_EDIT_CLEAR)`

**ON_OLECMD_COPY)**

Sendet den Befehl Copy bearbeiten. Als implementiert:

`ON_OLECMD(NULL, OLECMDID_COPY, ID_EDIT_COPY)`

**ON_OLECMD_CUT)**

Sendet den Befehl Cut bearbeiten. Als implementiert:

`ON_OLECMD(NULL, OLECMDID_CUT, ID_EDIT_CUT)`

**ON_OLECMD_NEW)**

Sendet die neue Datei-Befehl. Als implementiert:

`ON_OLECMD(NULL, OLECMDID_NEW, ID_FILE_NEW)`

**ON_OLECMD_OPEN)**

Sendet die Datei öffnen-Befehl. Als implementiert:

`ON_OLECMD(NULL, OLECMDID_OPEN, ID_FILE_OPEN)`

**ON_OLECMD_PAGESETUP)**

Sendet die Datei Seite Setup-Befehlsoption. Als implementiert:

`ON_OLECMD(NULL, OLECMDID_PAGESETUP, ID_FILE_PAGE_SETUP)`

**ON_OLECMD_PASTE)**

Sendet den Befehl Paste bearbeiten. Als implementiert:

`ON_OLECMD(NULL, OLECMDID_PASTE, ID_EDIT_PASTE)`

**ON_OLECMD_PASTESPECIAL)**

Sendet den Befehl Bearbeiten Inhalte einfügen. Als implementiert:

`ON_OLECMD(NULL, OLECMDID_PASTESPECIAL, ID_EDIT_PASTE_SPECIAL)`

**ON_OLECMD_PRINT)**

Sendet die Datei drucken-Befehl. Als implementiert:

`ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)`

**ON_OLECMD_PRINTPREVIEW)**

Sendet den Befehl "Datei Seitenansicht". Als implementiert:

`ON_OLECMD(NULL, OLECMDID_PRINTPREVIEW, ID_FILE_PRINT_PREVIEW)`

**ON_OLECMD_REDO)**

Sendet den Befehl Bearbeiten wiederherstellen. Als implementiert:

`ON_OLECMD(NULL, OLECMDID_REDO, ID_EDIT_REDO)`

**ON_OLECMD_SAVE)**

Sendet den Befehl Datei zu speichern. Als implementiert:

`ON_OLECMD(NULL, OLECMDID_SAVE, ID_FILE_SAVE)`

**ON_OLECMD_SAVE_AS)**

Sendet die Datei speichern unter-Befehl. Als implementiert:

`ON_OLECMD(NULL, OLECMDID_SAVEAS, ID_FILE_SAVE_AS)`

**ON_OLECMD_SAVE_COPY_AS)**

Sendet die Datei Kopie speichern unter-Befehl. Als implementiert:

`ON_OLECMD(NULL, OLECMDID_SAVECOPYAS, ID_FILE_SAVE_COPY_AS)`

**ON_OLECMD_SELECTALL)**

Sendet den Befehl wählen Sie alle bearbeiten. Als implementiert:

`ON_OLECMD(NULL, OLECMDID_SELECTALL, ID_EDIT_SELECT_ALL)`

**ON_OLECMD_UNDO)**

Sendet den Befehl Rückgängig bearbeiten. Als implementiert:

`ON_OLECMD(NULL, OLECMDID_UNDO, ID_EDIT_UNDO)`

### <a name="requirements"></a>Anforderungen

**Header:** afxdocob.h

### <a name="see-also"></a>Siehe auch

[COleCmdUI-Klasse](colecmdui-class.md)<br/>
[COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd)

## <a name="on_registered_message"></a>  ON_REGISTERED_MESSAGE

Die Windows `RegisterWindowMessage` Funktion wird verwendet, um eine neue Fensternachricht zu definieren, die garantiert im gesamten System eindeutig sein.

### <a name="syntax"></a>Syntax

```
ON_REGISTERED_MESSAGE( nMessageVariable, memberFxn )
```

### <a name="parameters"></a>Parameter

*nMessageVariable*<br/>
Die registrierten fenstermeldung-ID-Variable.

*memberFxn*<br/>
Der Name der Meldungshandler-Funktion, die die Nachricht zugeordnet ist.

### <a name="remarks"></a>Hinweise

Dieses Makro gibt an, welche Funktion wird die registrierte Meldung zu behandeln.

Weitere Informationen und Beispiele finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).

### <a name="example"></a>Beispiel

```cpp
static UINT NEAR WM_FIND = RegisterWindowMessage(_T("COMMDLG_FIND"));

BEGIN_MESSAGE_MAP(CMyWnd3, CWnd)
   ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
END_MESSAGE_MAP()
```

### <a name="requirements"></a>Anforderungen

**Header:** afxmsg_.h

### <a name="see-also"></a>Siehe auch

[RegisterWindowMessage registriert](https://msdn.microsoft.com/library/windows/desktop/ms644947)<br/>
[Benutzerdefinierte Handler](user-defined-handlers.md)

## <a name="on_registered_thread_message"></a>  ON_REGISTERED_THREAD_MESSAGE

Gibt an, welche Funktion behandelt die Meldung von der Windows-RegisterWindowMessage registriert-Funktion registriert.

### <a name="syntax"></a>Syntax

```
ON_REGISTERED_THREAD_MESSAGE(nMessageVariable, memberFxn )
```

### <a name="parameters"></a>Parameter

*nMessageVariable*<br/>
Die registrierten fenstermeldung-ID-Variable.

*memberFxn*<br/>
Der Name der Funktion CWinThread-Message-Handler, die die Nachricht zugeordnet ist.

### <a name="remarks"></a>Hinweise

RegisterWindowMessage registriert wird verwendet, um eine neue fenstermeldung definieren, die garantiert im gesamten System eindeutig sein. ON_REGISTERED_THREAD_MESSAGE muss anstelle von ON_REGISTERED_MESSAGE verwendet werden, wenn Sie eine CWinThread-Klasse haben.

### <a name="requirements"></a>Anforderungen

**Header:** afxmsg_.h

## <a name="on_thread_message"></a>  ON_THREAD_MESSAGE

Gibt an, welche Funktion eine benutzerdefinierte Meldung behandelt.

### <a name="syntax"></a>Syntax

```
ON_THREAD_MESSAGE( message, memberFxn )
```

### <a name="parameters"></a>Parameter

*message*<br/>
Die Meldungs-ID.

*memberFxn*<br/>
Der Name des der `CWinThread`-Message-Handler-Funktion, der die Nachricht zugeordnet ist.

### <a name="remarks"></a>Hinweise

ON_THREAD_MESSAGE muss anstelle von ON_MESSAGE verwendet werden, wenn Sie haben eine `CWinThread` Klasse. Benutzerdefinierte Meldungen sind alle Nachrichten, die nicht standardmäßige Windows-WM_MESSAGE Nachrichten sind. Es sollte genau eine ON_THREAD_MESSAGE-Makro-Anweisung in der meldungszuordnung für jede benutzerdefinierte Nachricht, die eine Message-Handler-Funktion zugeordnet werden muss.

### <a name="requirements"></a>Anforderungen

**Header:** afxole.h

## <a name="on_update_command_ui"></a>  ON_UPDATE_COMMAND_UI

Dieses Makro gibt an, welche Funktion eine Benutzeroberflächen-Update-Befehlsnachricht behandelt.

### <a name="syntax"></a>Syntax

```
ON_UPDATE_COMMAND_UI( id, memberFxn )
```

### <a name="parameters"></a>Parameter

*ID*<br/>
Die Meldungs-ID.

*memberFxn*<br/>
Der Name der Meldungshandler-Funktion, die die Nachricht zugeordnet ist.

### <a name="remarks"></a>Hinweise

Es sollte genau eine ON_UPDATE_COMMAND_UI-Makro-Anweisung in der meldungszuordnung für jeden Benutzeroberflächen-Update-Befehl, der eine Message-Handler-Funktion zugeordnet werden muss.

Weitere Informationen und Beispiele finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).

### <a name="requirements"></a>Anforderungen

**Header:** afxole.h

### <a name="see-also"></a>Siehe auch

[CCmdUI-Klasse](ccmdui-class.md)

## <a name="on_command_range"></a>  ON_COMMAND_RANGE

Verwenden Sie dieses Makro, um einen zusammenhängenden Bereich von Befehls-IDs für eine einzelne Nachricht Handler-Funktion zuzuordnen.

### <a name="syntax"></a>Syntax

```
ON_COMMAND_RANGE( id1, id2, memberFxn )
```

### <a name="parameters"></a>Parameter

*"id1"*<br/>
Befehls-ID am Anfang des einen zusammenhängenden Bereich von Befehls-IDs.

*"id2"*<br/>
Befehls-ID am Ende einen zusammenhängenden Bereich von Befehls-IDs.

*memberFxn*<br/>
Der Name der Meldungshandler-Funktion, die die Befehle zugeordnet sind.

### <a name="remarks"></a>Hinweise

Die ID-Bereich beginnt mit *"id1"* und endet mit *id2*.

Verwenden Sie ON_COMMAND_RANGE, um einen Bereich für Befehls-IDs auf eine Memberfunktion zuzuordnen. Verwendung [ON_COMMAND](#on_command) um einen einzelnen Befehl auf eine Memberfunktion zuzuordnen. Nur ein Meldungszuordnungseintrags kann eine angegebenen Befehls-ID überein. Sie können nicht mehr als einen Handler, also einen Befehl zuordnen. Weitere Informationen zum Mapping meldungsbereiche, finden Sie unter [Handler für Meldungszuordnungsbereiche](../../mfc/handlers-for-message-map-ranges.md).

Es gibt keine automatische Unterstützung für Meldungszuordnungsbereiche, damit Sie das Makro selbst platzieren müssen.

### <a name="example"></a>Beispiel

```cpp
// The code fragment below shows how to use ON_COMMAND_RANGE macro
// to map a contiguous range of command IDs to a single message
// handler function (i.e. OnRangeCmds() in the sample below). In
// addition, it also shows how to use CheckMenuRadioItem() to check a
// selected menu item and makes it a radio item.

BEGIN_MESSAGE_MAP(CChildFrame, CMDIChildWnd)
   ON_COMMAND_RANGE(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3, &CChildFrame::OnRangeCmds)
END_MESSAGE_MAP()

void CChildFrame::OnRangeCmds(UINT nID)
{
   CMenu* mmenu = AfxGetMainWnd()->GetMenu();
   CMenu* submenu = mmenu->GetSubMenu(5);
   submenu->CheckMenuRadioItem(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3,
      nID, MF_BYCOMMAND);
}
```

### <a name="requirements"></a>Anforderungen

**Header:** afxmsg_.h

## <a name="on_update_command_ui_range"></a>  ON_UPDATE_COMMAND_UI_RANGE

Ordnet einen zusammenhängenden Bereich von Befehls-IDs ein einzelnes Update Message-Handler-Funktion.

### <a name="syntax"></a>Syntax

```
ON_UPDATE_COMMAND_UI_RANGE( id1, id2, memberFxn )
```

### <a name="parameters"></a>Parameter

*"id1"*<br/>
Befehls-ID am Anfang des einen zusammenhängenden Bereich von Befehls-IDs.

*"id2"*<br/>
Befehls-ID am Ende einen zusammenhängenden Bereich von Befehls-IDs.

*memberFxn*<br/>
Der Name der Update-Nachrichtenhandler-Funktion, die die Befehle zugeordnet sind.

### <a name="remarks"></a>Hinweise

Update-Meldungshandler aktualisieren Sie den Status der Menüelemente und Symbolleisten-Schaltflächen, die dem Befehl zugeordnet. Die ID-Bereich beginnt mit *"id1"* und endet mit *id2*.

Es gibt keine automatische Unterstützung für Meldungszuordnungsbereiche, damit Sie das Makro selbst platzieren müssen.

### <a name="requirements"></a>Anforderungen

**Header:** afxmsg_.h

## <a name="on_control_range"></a>  ON_CONTROL_RANGE

Verwenden Sie dieses Makro, um einen zusammenhängenden Bereich von Steuerelement-IDs für eine einzelne Nachricht Handler-Funktion für eine angegebene Windows-benachrichtigungsmeldung, wie z. B. BN_CLICKED zuzuordnen.

### <a name="syntax"></a>Syntax

```
ON_CONTROL_RANGE( wNotifyCode, id1, id2, memberFxn )
```

### <a name="parameters"></a>Parameter

*wNotifyCode schalten*<br/>
Der Benachrichtigungscode, der auf dem der Handler geantwortet wird.

*"id1"*<br/>
Befehls-ID am Anfang des einen zusammenhängenden Bereich von Steuerelement-IDs.

*"id2"*<br/>
Befehls-ID am Ende einen zusammenhängenden Bereich von Steuerelement-IDs.

*memberFxn*<br/>
Der Name der Meldungshandler-Funktion, die die Steuerelemente zugeordnet sind.

### <a name="remarks"></a>Hinweise

Die ID-Bereich beginnt mit *"id1"* und endet mit *id2*. Der Ereignishandler für die angegebene Benachrichtigung, die von einem der zugeordneten Steuerelemente aufgerufen.

Es gibt keine automatische Unterstützung für Meldungszuordnungsbereiche, damit Sie das Makro selbst platzieren müssen.

Weitere Informationen zum Implementieren von Handlerfunktionen für einen Bereich von Steuerelement-IDs finden Sie unter [Handler für Meldungszuordnungsbereiche](../../mfc/handlers-for-message-map-ranges.md).

### <a name="requirements"></a>Anforderungen

**Header:** afxmsg_.h
