---
title: CWordArray-Klasse
ms.date: 11/04/2016
f1_keywords:
- CWordArray
- AFXCOLL/CWordArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: 2ba2c194-2c6c-40ff-9db4-e9dbe57e1f57
ms.openlocfilehash: 945a77436f41f4981392e583c831723e667f867c
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58770574"
---
# <a name="cwordarray-class"></a>CWordArray-Klasse

Unterstützt Arrays mit 16-Bit-Wörtern.

## <a name="syntax"></a>Syntax

```
class CWordArray : public CObject
```

## <a name="members"></a>Member

Die Memberfunktionen der `CWordArray` ähneln den Memberfunktionen der Klasse [CObArray](../../mfc/reference/cobarray-class.md). Aufgrund dieser Ähnlichkeit können Sie die `CObArray`-Referenzdokumentation für Memberfunktionsbesonderheiten verwenden. Immer dort, wo ein [CObject](../../mfc/reference/cobject-class.md) Zeiger als Funktionsparameter oder Rückgabewert, ersetzen Sie ein Wort.

`CObject* CObArray::GetAt( int <nIndex> ) const;`

Beispielsweise übersetzt zu

`WORD CWordArray::GetAt( int <nIndex> ) const;`

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|Erstellt ein leeres Array.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|Fügt am Ende des Arrays ein Element hinzu; vergrößert das Array bei Bedarf.|
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|Hängt ein anderes Array an das Array an; vergrößert das Array bei Bedarf.|
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|Kopiert ein anderes Array in das Array; vergrößert das Array bei Bedarf.|
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Gibt einen temporären Verweis auf den Elementzeiger innerhalb des Arrays zurück.|
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Gibt den gesamten nicht verwendeten Arbeitsspeicher über der aktuellen Obergrenze frei.|
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|Gibt den Wert an einem bestimmten Index zurück.|
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Ruft die Anzahl der Elemente im Array ab.|
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|Ermöglicht den Zugriff auf Elemente im Array. NULL kann sein.|
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|Ruft die Anzahl der Elemente im Array ab.|
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|Gibt den größten gültigen Index zurück.|
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Fügt ein Element (oder alle Elemente in einem anderen Array) am angegebenen Index ein.|
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|Bestimmt, ob das Array leer ist.|
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Entfernt alle Elemente aus diesem Array.|
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Entfernt ein Element an einem spezifischen Index.|
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|Legt den Wert für einen bestimmten Index fest; Array darf nicht vergrößert werden.|
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|Legt den Wert für einen bestimmten Index fest; vergrößert das Array bei Bedarf.|
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|Legt die Anzahl der Elemente im Array fest.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CObArray::operator &#91;&#93;](../../mfc/reference/cobarray-class.md#operator_at)|Legt das Element am angegebenen Index fest oder ruft es ab.|

## <a name="remarks"></a>Hinweise

`CWordArray` enthält die [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) Makro, um Serialisierung und die Sicherung der Elemente zu unterstützen. Wenn ein Array von Worten gespeichert ist, in ein Archiv, das entweder mit einem überladenen Operator zum Einfügen oder mit der [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) Memberfunktion wird jedes Element ist, was wiederum serialisiert.

> [!NOTE]
>  Vor dem Verwenden eines Arrays, verwenden Sie `SetSize`, um dessen Größe festzustellen, und weisen dafür Arbeitsspeicher zu. Wenn Sie `SetSize` nicht verwenden, kann das Hinzufügen von Elementen zu Ihrem Array dazu führen, dass es häufig neu zugeordnet und kopiert wird. Häufige Neuzuordnungen und Kopiervorgänge sind ineffizient und können zu einer Fragmentierung des Arbeitsspeichers führen.

Wenn Sie eine Sicherung der einzelnen Elemente im Array benötigen, müssen Sie die Tiefe des sicherungskontexts auf 1 oder größer festlegen.

Weitere Informationen zur Verwendung von `CWordArray`, finden Sie im Artikel [Sammlungen](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CWordArray`

## <a name="requirements"></a>Anforderungen

**Header:** afxcoll.h

##  <a name="icommandsource_interface"></a>  ICommandSource-Schnittstelle

Verwaltet die Befehle, die von einem Quellobjekt für den Befehl zu einem Benutzersteuerelement gesendet.

```
interface class ICommandSource
```

### <a name="remarks"></a>Hinweise

Beim Hosten eines Benutzersteuerelements in MFC-Ansicht, [CWinFormsView-Klasse](../../mfc/reference/cwinformsview-class.md) Routen Befehle und Update-Befehl UI-Nachrichten an das Steuerelement, damit Sie die MFC-Befehle (z. B. Frame Menüelemente und Symbolleistenschaltflächen) verarbeiten kann. Durch die Implementierung, Sie geben dem Benutzersteuerelement einen Verweis auf die `ICommandSource` Objekt.

Weitere Informationen finden Sie unter [How to: Hinzufügen von Befehlsrouting an der Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zur Verwendung für `ICommandTarget`.

Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [verwenden ein Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="addcommandhandler"></a>  ICommandSource::AddCommandHandler

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

Diese Methode fügt den Befehlshandler *CmdHandler* auf das Befehlsquellobjekt und ordnet Sie den Handler, der *CmdID*.

Weitere Informationen finden Sie unter [How to: Hinzufügen von Befehlsrouting an der Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zur Verwendung für `AddCommandHandler`.

##  <a name="addcommandrangehandler"></a>  ICommandSource::AddCommandRangeHandler

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

##  <a name="addcommandrangeuihandler"></a>  ICommandSource::AddCommandRangeUIHandler

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

##  <a name="addcommanduihandler"></a>  ICommandSource::AddCommandUIHandler

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

Diese Methode fügt den Benutzer Schnittstelle Befehlshandler Nachricht *CmdHandler* auf das Befehlsquellobjekt und ordnet Sie den Handler, der *CmdID*.

##  <a name="postcommand"></a>  ICommandSource::PostCommand

Sendet eine Nachricht ohne zu warten, bis es verarbeitet werden.

```
void PostCommand(unsigned int command);
```

### <a name="parameters"></a>Parameter

*command*<br/>
Die Befehls-ID der Nachricht, die gepostet werden soll.

### <a name="remarks"></a>Hinweise

Diese Methode asynchron sendet die Nachricht, die die angegebene ID zugeordnet *Befehl*. Ruft [CWnd::PostMessage](../../mfc/reference/cwnd-class.md#postmessage) die Nachricht in Message Queue und anschließend zurück des Fensters angeordnet werden, ohne zu warten, für das entsprechende Fenster zur Verarbeitung der Nachricht.

##  <a name="removecommandhandler"></a>  ICommandSource::RemoveCommandHandler

Entfernt einen Befehlshandler von einem Befehl-Quellobjekt.

```
void RemoveCommandHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Parameter

*cmdID*<br/>
Die Befehls-ID.

### <a name="remarks"></a>Hinweise

Diese Methode entfernt, die den Befehlshandler zugeordnet *CmdID* aus dem Quellobjekt für den Befehl.

##  <a name="removecommandrangehandler"></a>  ICommandSource::RemoveCommandRangeHandler

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

Diese Methode entfernt eine Gruppe von nachrichtenhandlern aufbauen, die anhand des Befehls-IDs zugeordnet *CmdIDMin* und *CmdIDMax*, aus dem Quellobjekt für den Befehl.

##  <a name="removecommandrangeuihandler"></a>  ICommandSource::RemoveCommandRangeUIHandler

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

Diese Methode entfernt eine Gruppe von Benutzer-Schnittstelle Befehl nachrichtenhandlern aufbauen, die anhand des Befehls-IDs zugeordnet *CmdIDMin* und *CmdIDMax*, aus dem Quellobjekt für den Befehl.

##  <a name="removecommanduihandler"></a>  ICommandSource::RemoveCommandUIHandler

Entfernt einen Benutzer Schnittstelle Befehlshandler Nachricht von einem Quellobjekt für den Befehl.

```
void RemoveCommandUIHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Parameter

*cmdID*<br/>
Die Befehls-ID.

### <a name="remarks"></a>Hinweise

Diese Methode entfernt den Benutzer Schnittstelle Nachricht Befehlshandler zugeordnet *CmdID* aus dem Quellobjekt für den Befehl.

##  <a name="sendcommand"></a>  ICommandSource::SendCommand

Sendet eine Nachricht und wartet darauf, dass sie vor der Rückgabe verarbeitet werden.

```
void SendCommand(unsigned int command);
```

### <a name="parameters"></a>Parameter

*command*<br/>
Die Befehls-ID der Nachricht gesendet werden.

### <a name="remarks"></a>Hinweise

Diese Methode synchron sendet die Nachricht, die die angegebene ID zugeordnet *Befehl*. Ruft [Funktion CWnd:: SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) , platzieren Sie die Nachricht in Message Queue und Wartevorgänge des Fensters, bis diese Fensterprozedur die Meldung vor der Rückgabe verarbeitet hat.

##  <a name="icommandtarget_interface"></a>  ICommandTarget-Schnittstelle

Stellt ein Steuerelement mit einer Schnittstelle empfangen Befehle von einem Befehlsquellobjekt bereit.

```
interface class ICommandTarget
```

### <a name="remarks"></a>Hinweise

Beim Hosten eines Benutzersteuerelements in MFC-Ansicht, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) Routen Befehle und Update-Befehl UI-Nachrichten an das Steuerelement, damit Sie die MFC-Befehle (z. B. Frame Menüelemente und Symbolleistenschaltflächen) verarbeiten kann. Durch die Implementierung `ICommandTarget`, geben Sie dem Benutzersteuerelement einen Verweis auf das Objekt.

Weitere Informationen finden Sie unter [How to: Hinzufügen von Befehlsrouting an der Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zur Verwendung für `ICommandTarget`.

Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [verwenden ein Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="initialize"></a>  ICommandTarget:: Initialize

Initialisiert das Zielobjekt für den Befehl.

```
void Initialize(ICommandSource^ cmdSource);
```

### <a name="parameters"></a>Parameter

*cmdSource*<br/>
Ein Handle für das Befehlsquellobjekt.

### <a name="remarks"></a>Hinweise

Beim Hosten eines Benutzersteuerelements in MFC-Ansicht, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) Routen Befehle und Update-Befehl UI-Nachrichten an das Steuerelement, damit Sie die MFC-Befehle verarbeiten kann.

Diese Methode das Zielobjekt für den Befehl initialisiert und das Quellobjekt für den angegebenen Befehl ordnet *CmdSource*. Es sollte in der Implementierung der Benutzer Control-Klasse aufgerufen werden. Bei der Initialisierung, sollten Sie Befehlshandler mit das Befehlsquellobjekt registrieren, durch den Aufruf [ICommandSource::AddCommandHandler](../../mfc/reference/icommandsource-interface.md) in die `Initialize` Implementierung. Weitere Informationen finden Sie unter [How to: Hinzufügen von Befehlsrouting an der Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zur Verwendung für `Initialize` dazu.

##  <a name="icommandui_interface"></a>  ICommandUI-Schnittstelle

Verwaltet von Befehlen der Benutzeroberfläche.

```
interface class ICommandUI
```

### <a name="remarks"></a>Hinweise

Diese Schnittstelle bietet Methoden und Eigenschaften, die Befehlen der Benutzeroberfläche zu verwalten. `ICommandUI` ist vergleichbar mit [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md), außer dass `ICommandUI` dient für MFC-Anwendungen, die mit .NET Komponenten zusammenwirken.

`ICommandUI` wird verwendet, in eine `ON_UPDATE_COMMAND_UI` Handler in einer - abgeleiteten Klasse. Wenn ein Benutzer einer Anwendung (SELECT-Anweisungen oder Klicks) aktiviert wird ein Menü, das jedes Menüelement im angezeigt, als aktiviert oder deaktiviert. Das Ziel der einzelnen Menübefehle im bietet diese Informationen durch die Implementierung einer `ON_UPDATE_COMMAND_UI` Handler. Verwenden Sie das Fenster "Eigenschaften" für jeden Befehl Schnittstelle Benutzerobjekte in Ihrer Anwendung zum Erstellen eines Meldungszuordnungseintrags und Funktionsprototyp für jeden Handler.

Weitere Informationen darüber, wie der `ICommandUI` Schnittstelle wird verwendet, in das Befehlsrouting, finden Sie unter [Vorgehensweise: Befehl "hinzufügen" Routing an das Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).

Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [verwenden ein Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

Weitere Informationen dazu, wie Befehlen der Benutzeroberfläche in MFC verwaltet werden, finden Sie unter [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md).

##  <a name="check"></a>  ICommandUI::Check

Legt die Benutzeroberflächenelemente für diesen Befehl auf den entsprechenden Aktivierungszustand fest.

```
property UICheckState Check;
```

### <a name="remarks"></a>Hinweise

Diese Eigenschaft legt die Benutzeroberflächenelemente für diesen Befehl auf den entsprechenden Aktivierungszustand an. Legen Sie `Check` auf die folgenden Werte:

|Begriff|Definition|
|----------|----------------|
|0|Deaktivieren Sie|
|1|Azure Functions|
|2|Legen Sie unbestimmt|

##  <a name="continuerouting"></a>  ICommandUI::ContinueRouting

Weist den Befehl Routingmechanismus dar, um den Vorgang fortzusetzen, routing von der aktuellen Nachricht der Vererbungskette von Handlern.

```
void ContinueRouting();
```

### <a name="remarks"></a>Hinweise

Dies ist eine erweiterte Memberfunktion, die in Verbindung mit verwendet werden, sollte ein [ON_COMMAND_EX](message-map-macros-mfc.md#on_command_ex) Handler, der "false" zurückgibt. Weitere Informationen finden Sie im technischen Hinweis [TN006: Meldungszuordnungen](../../mfc/tn006-message-maps.md).

##  <a name="enabled"></a>  ICommandUI::Enabled

Aktiviert oder deaktiviert die Benutzeroberflächenelemente für diesen Befehl.

```
property bool Enabled;
```

### <a name="remarks"></a>Hinweise

Diese Eigenschaft aktiviert oder deaktiviert die Benutzeroberflächenelemente für diesen Befehl. Legen Sie `Enabled` auf "true", um das Element "false" zu aktivieren, um ihn zu deaktivieren.

##  <a name="id"></a>  ICommandUI::ID

Ruft die ID des Benutzerobjekts für die Schnittstelle dargestellt, durch die `ICommandUI` Objekt.

```
property unsigned int ID;
```

### <a name="remarks"></a>Hinweise

Diese Eigenschaft ruft die ID (ein Handle) des Menüelements, Symbolleisten-Schaltfläche ab oder anderen Benutzeroberflächen-Objekt dargestellt wird, durch die `ICommandUI` Objekt.

##  <a name="index"></a>  ICommandUI::Index

Ruft den Index des das Benutzeroberflächenobjekt, dargestellt durch die `ICommandUI` Objekt.

```
property unsigned int Index;
```

### <a name="remarks"></a>Hinweise

Diese Eigenschaft ruft den Index (ein Handle) des Menüelements, Symbolleisten-Schaltfläche ab oder anderen Benutzeroberflächen-Objekt dargestellt wird, durch die `ICommandUI` Objekt.

##  <a name="radio"></a>  ICommandUI::Radio

Legt die Benutzeroberflächenelemente für diesen Befehl auf den entsprechenden Aktivierungszustand fest.

```
property bool Radio;
```

### <a name="remarks"></a>Hinweise

Diese Eigenschaft legt die Benutzeroberflächenelemente für diesen Befehl auf den entsprechenden Aktivierungszustand an. Legen Sie `Radio` auf "true", um die; andernfalls "false" zu aktivieren.

##  <a name="text"></a>  ICommandUI::Text

Legt den Text der Benutzeroberflächenelemente für diesen Befehl fest.

```
property String^ Text;
```

### <a name="remarks"></a>Hinweise

Diese Eigenschaft legt den Text der Benutzeroberflächenelemente für diesen Befehl. Legen Sie `Text` auf ein Text-Zeichenfolge-Handle.

##  <a name="iview_interface"></a>  IView-Schnittstelle

Implementiert einige Methoden, die [CWinFormsView](../../mfc/reference/cwinformsview-class.md) zum Senden von Benachrichtigungen anzeigen an einem verwalteten Steuerelement verwendet.

```
interface class IView
```

### <a name="remarks"></a>Hinweise

`IView` implementiert einige Methoden, die `CWinFormsView` verwendet, um eine allgemeine Ansicht Benachrichtigungen zu einem gehosteten verwalteten Steuerelement weitergeleitet. Hierbei handelt es sich [OnInitialUpdate](../../mfc/reference/iview-interface.md), [OnUpdate](../../mfc/reference/iview-interface.md) und [OnActivateView](../../mfc/reference/iview-interface.md).

`IView` ist vergleichbar mit [CView](../../mfc/reference/cview-class.md), jedoch nur mit verwalteten Ansichten und Steuerelementen verwendet wird.

Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [verwenden ein Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="onactivateview"></a>  IView::OnActivateView

Wird von MFC aufgerufen, wenn eine Ansicht aktiviert oder deaktiviert ist.

```
void OnActivateView(bool activate);
```

### <a name="parameters"></a>Parameter

*activate*<br/>
Gibt an, ob die Sicht wird aktiviert oder deaktiviert.

##  <a name="oninitialupdate"></a>  IView:: OnInitialUpdate

Vom Framework aufgerufen, nachdem die Ansicht zuerst auf das Dokument angefügt ist, aber vor die Ansicht angezeigt wird.

```
void OnInitialUpdate();
```

##  <a name="onupdate"></a>  IView::OnUpdate

Von MFC aufgerufen, nachdem das Dokument von der Ansicht geändert wurde.

```
void OnUpdate();
```

### <a name="remarks"></a>Hinweise

Diese Funktion kann es sich um die Ansicht seine Anzeige Änderungen entsprechend aktualisiert.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel erfassen](../../overview/visual-cpp-samples.md)<br/>
[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
