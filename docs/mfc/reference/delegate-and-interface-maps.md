---
title: Delegaten und Schnittstelle Zuordnungsmakros (MFC)
ms.date: 03/30/2017
helpviewer_keywords:
- delegate map macros [MFC]
- event map macros [MFC]
- interface map macros [MFC]
ms.assetid: 3840e642-ff7d-4bdc-998b-c7d8fc50890e
ms.openlocfilehash: 91bd50ca34893b7dd91f6402f5ca95865f872650
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429340"
---
|||
|-|-|
|[BEGIN_DELEGATE_MAP](#begin_delegate_map)|Beginnt eine Zuordnung von Delegaten.|
|[BEGIN_INTERFACE_MAP](#begin_interface_map)|Der Beginn der Definition der interfaced Zuordnung.|
|[CommandHandler-Delegat](#commandhandler)|Registriert eine Befehlsquelle Rückrufmethoden.  |
|[END_DELEGATE_MAP](#end_delegate_map)|Eine Delegat-Zuordnung wird beendet.|
|[END_INTERFACE_MAP](#end_interface_map)|Beendet die schnittstellenzuordnung in der Implementierungsdatei hinzu. |
|[EVENT_DELEGATE_ENTRY](#event_delegate_entry)|Erstellt einen Eintrag in der Zuordnung des Delegaten an.|
|[INTERFACE_PART](#interface_part)|Zwischen der BEGIN_INTERFACE_MAP-Makro und das END_INTERFACE_MAP-Makro verwendet, für jede Schnittstelle, die von Ihrem Objekt unterstützt werden.|
|[MAKE_DELEGATE](#make_delegate)|Fügt einen Ereignishandler an ein verwaltetes Steuerelement an.|

## <a name="begin_delegate_map"></a> BEGIN_DELEGATE_MAP

Beginnt eine Zuordnung von Delegaten.

### <a name="syntax"></a>Syntax

```
BEGIN_DELEGATE_MAP(  CLASS );
```

### <a name="parameters"></a>Parameter

*KLASSE*<br/>
Die Klasse, die in der das verwaltete Steuerelement gehostet wird.

### <a name="remarks"></a>Hinweise

Dieses Makro markiert den Anfang einer Liste von Einträgen für Delegaten, die eine Zuordnung Delegaten bilden. Ein Beispiel, wie dieses Makro verwendet wird, finden Sie unter [EVENT_DELEGATE_ENTRY](#event_delegate_entry).

### <a name="requirements"></a>Anforderungen

**Header:** msclr\event.h

### <a name="see-also"></a>Siehe auch

[Vorgehensweise: Auffangen von Windows Forms-Ereignissen aus nativen C++-Klassen](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

##  <a name="begin_interface_map"></a>BEGIN_INTERFACE_MAP

Der Beginn der Definition der interfaced Zuordnung in der Implementierungsdatei verwendet.

### <a name="syntax"></a>Syntax

```
BEGIN_INTERFACE_MAP( theClass, baseClass )
```

### <a name="parameters"></a>Parameter

*theClass*<br/>
Die Klasse, in der die Schnittstellenzuordnung definiert werden soll

*Basisklasse*<br/>
Die Klasse, von der *TheClass* abgeleitet.

### <a name="remarks"></a>Hinweise

Für jede Schnittstelle, die implementiert wird, gibt es eine oder mehrere Aufrufe der INTERFACE_PART-Makro. Für jedes Aggregat, das die Klasse verwendet, gibt es einen einzelnen INTERFACE_AGGREGATE-Makro-Aufruf.

Weitere Informationen zu schnittstellenzuordnungen, finden Sie unter [technischen Hinweis 38](../tn038-mfc-ole-iunknown-implementation.md).

### <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="commandhandler"></a>CommandHandler-Delegat

Registriert eine Befehlsquelle Rückrufmethoden.

### <a name="syntax"></a>Syntax

```
delegate void CommandHandler(  UINT^ cmdID  );
```

### <a name="parameters"></a>Parameter

*cmdID*<br/>
Die Befehls-ID.

### <a name="remarks"></a>Hinweise

Dieser Delegat registriert eine Befehlsquelle Rückrufmethoden. Wenn Sie einen Delegaten an das Quellobjekt für den Befehl hinzufügen, wird die Callback-Methode einen Handler für Befehle, die aus der angegebenen Quelle stammen.

Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen Befehlsrouting an der Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).

Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [verwenden ein Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Anforderungen

**Header:** afxwinforms.h (definiert in der Assembly atlmfc\lib\mfcmifc80.dll)

### <a name="see-also"></a>Siehe auch

[Vorgehensweise: Hinzufügen von Befehlsrouting zum Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)

##  <a name="commanduihandler"></a>CommandUIHandler

Registriert Rückrufmethoden bereit, mit einer benutzermeldung Schnittstelle Update-Befehl.

### <a name="syntax"></a>Syntax

```
delegate void CommandUIHandler(  unsigned int cmdID, ICommandUI^ cmdUI);
```

### <a name="parameters"></a>Parameter

*cmdID*<br/>
Die Befehls-ID.

*cmdUI*<br/>
Der Befehl Nachrichten-ID

### <a name="remarks"></a>Hinweise

Dieser Delegat registriert Rückrufmethoden bereit, mit einer benutzermeldung Schnittstelle Update-Befehl. `CommandUIHandler` ist vergleichbar mit [CommandHandler](#commandhandler) mit dem Unterschied, dass dieser Delegat mit Befehlen der Benutzeroberfläche Objekt Update verwendet wird. Update Befehlen der Benutzeroberfläche sollten mit Ereignishandlermethoden Nachricht 1: 1 zugeordnet werden.

Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [verwenden ein Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Anforderungen

**Header:** afxwinforms.h (definiert in der Assembly atlmfc\lib\mfcmifc80.dll)

### <a name="see-also"></a>Siehe auch

[Vorgehensweise: Hinzufügen von Befehlsrouting zum Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[CommandHandler](#commandhandler)

##  <a name="end_delegate_map"></a>END_DELEGATE_MAP

Eine Delegat-Zuordnung wird beendet.

### <a name="syntax"></a>Syntax

```
END_DELEGATE_MAP();
```

### <a name="remarks"></a>Hinweise

Dieses Makro markiert das Ende einer Liste von Einträgen für Delegaten, die eine Zuordnung Delegaten bilden. Ein Beispiel, wie dieses Makro verwendet wird, finden Sie unter [EVENT_DELEGATE_ENTRY](#event_delegate_entry).

### <a name="requirements"></a>Anforderungen

**Header:** msclr\event.h

### <a name="see-also"></a>Siehe auch

[Vorgehensweise: Auffangen von Windows Forms-Ereignissen aus nativen C++-Klassen](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

##  <a name="end_interface_map"></a>END_INTERFACE_MAP

Beendet die schnittstellenzuordnung in der Implementierungsdatei hinzu.

### <a name="syntax"></a>Syntax

```
END_INTERFACE_MAP( )
```

### <a name="remarks"></a>Hinweise

Weitere Informationen zu schnittstellenzuordnungen, finden Sie unter [technischen Hinweis 38](../tn038-mfc-ole-iunknown-implementation.md).

### <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

### <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](mfc-macros-and-globals.md)<br/>
[BEGIN_INTERFACE_MAP](#begin_interface_map)

##  <a name="event_delegate_entry"></a>EVENT_DELEGATE_ENTRY

Erstellt einen Eintrag in der Zuordnung des Delegaten an.

### <a name="syntax"></a>Syntax

```
EVENT_DELEGATE_ENTRY(MEMBER, ARG0, ARG1);
```

### <a name="parameters"></a>Parameter

*MEMBER*<br/>
Die Ereignishandlermethode für das Steuerelement angefügt werden.

*ARG0*<br/>
Das erste Argument von der verwalteten Ereignishandlermethode, z. B. `Object^`.

*ARG1*<br/>
Das zweite Argument der Handlermethode verwaltetes Ereignis, z. B. `EventArgs^`.

### <a name="remarks"></a>Hinweise

Jeder Eintrag in der Zuordnung des Delegaten entspricht einem verwalteten Ereignishandlerdelegaten erstellt [MAKE_DELEGATE](#make_delegate).

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird veranschaulicht, wie EVENT_DELEGATE_ENTRY verwenden, erstellen Sie einen Eintrag in der Zuordnung der Delegat für die `OnClick` Ereignishandler; außerdem finden Sie im Codebeispiel unter MAKE_DELEGATE. Weitere Informationen finden Sie unter [Vorgehensweise: Auffangen von Windows Forms-Ereignissen aus systemeigenen C++-Klassen](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md).

```cpp
BEGIN_DELEGATE_MAP(CMyView)
   EVENT_DELEGATE_ENTRY(OnClick, System::Object^, System::EventArgs^)
END_DELEGATE_MAP()

```

### <a name="requirements"></a>Anforderungen

**Header:** msclr\event.h

### <a name="see-also"></a>Siehe auch

[MAKE_DELEGATE](#make_delegate)<br/>
[BEGIN_DELEGATE_MAP](#begin_delegate_map)<br/>
[END_DELEGATE_MAP](#end_delegate_map)

##  <a name="interface_part"></a>INTERFACE_PART

Zwischen der BEGIN_INTERFACE_MAP-Makro und das END_INTERFACE_MAP-Makro verwendet, für jede Schnittstelle, die von Ihrem Objekt unterstützt werden.

### <a name="syntax"></a>Syntax

```
INTERFACE_PART( theClass, iid, localClass)
```

### <a name="parameters"></a>Parameter

*theClass*<br/>
Der Name der Klasse, die die Schnittstellenzuordnung enthält.
*IID*<br/>
Die IID, die der eingebetteten Klasse zugeordnet werden soll.
*localClass*<br/>
Der Name der lokalen Klasse.

### <a name="remarks"></a>Hinweise

Sie können ein Member der Klasse angegeben werden, indem Sie eine IID zugeordnet *TheClass* und *LocalClass*.

Weitere Informationen zu schnittstellenzuordnungen, finden Sie unter [technischen Hinweis 38](../tn038-mfc-ole-iunknown-implementation.md).

### <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="make_delegate"></a>MAKE_DELEGATE

Fügt einen Ereignishandler an ein verwaltetes Steuerelement an.

### <a name="syntax"></a>Syntax

```
MAKE_DELEGATE( DELEGATE,  MEMBER) ;
```

### <a name="parameters"></a>Parameter

*DELEGATEN*<br/>
Der Typ des verwalteten-ereignishandlers zu delegieren, z. B. [EventHandler](assetId:///T:System.EventHandler?qualifyHint=False&autoUpgrade=True).

*MEMBER*<br/>
Der Name der Ereignishandlermethode für das Steuerelement angefügt werden.

### <a name="remarks"></a>Hinweise

Dieses Makro erstellt ein verwaltetes Ereignishandler-Delegat vom Typ *DELEGIEREN* und mit dem Namen *MEMBER*. Der verwaltetes Ereignis-Handler-Delegat kann es sich um eine systemeigene Klasse zum Behandeln von verwalteter Ereignissen.

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird veranschaulicht, wie aufzurufende `MAKE_DELEGATE` zum Anfügen einer `OnClick` -Ereignishandler zu einem MFC-Steuerelement `MyControl`. Eine umfassendere Erläuterung der Funktionsweise dieses Makro in einer MFC-Anwendung, finden Sie unter [Vorgehensweise: Auffangen von Windows Forms-Ereignissen aus systemeigenen C++-Klassen](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md).

```cpp
// CMyView derives from CWinFormsView.
void CMyView::OnInitialUpdate()
{
   CWinFormsView::OnInitialUpdate();

   GetControl()->Click += MAKE_DELEGATE(System::EventHandler, OnClick);
}
```

### <a name="requirements"></a>Anforderungen

**Header:** msclr\event.h

### <a name="see-also"></a>Siehe auch

[BEGIN_DELEGATE_MAP](#begin_delegate_map)<br/>
[END_DELEGATE_MAP](#end_delegate_map)<br/>
[EVENT_DELEGATE_ENTRY](#event_delegate_entry)

