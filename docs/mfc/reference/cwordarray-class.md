---
title: CWordArray-Klasse
ms.date: 09/07/2019
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
ms.openlocfilehash: c136bbb14e0d7cffc604813731b6f87ba18063cf
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907911"
---
# <a name="cwordarray-class"></a>CWordArray-Klasse

Unterstützt Arrays mit 16-Bit-Wörtern.

## <a name="syntax"></a>Syntax

```
class CWordArray : public CObject
```

## <a name="members"></a>Member

Die Member-Funktionen `CWordArray` von ähneln den Element Funktionen der-Klasse [kobarray](../../mfc/reference/cobarray-class.md). Aufgrund dieser Ähnlichkeit können Sie die `CObArray`-Referenzdokumentation für Memberfunktionsbesonderheiten verwenden. Wenn ein [CObject](../../mfc/reference/cobject-class.md) -Zeiger als Funktionsparameter oder Rückgabewert angezeigt wird, ersetzen Sie ein Wort.

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
|[CObArray:: Append](../../mfc/reference/cobarray-class.md#append)|Hängt ein anderes Array an das Array an; vergrößert das Array bei Bedarf.|
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|Kopiert ein anderes Array in das Array; vergrößert das Array bei Bedarf.|
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Gibt einen temporären Verweis auf den Elementzeiger innerhalb des Arrays zurück.|
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Gibt den gesamten nicht verwendeten Arbeitsspeicher über der aktuellen Obergrenze frei.|
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|Gibt den Wert an einem bestimmten Index zurück.|
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Ruft die Anzahl der Elemente im Array ab.|
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|Ermöglicht den Zugriff auf Elemente im Array. Kann NULL sein.|
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|Ruft die Anzahl der Elemente im Array ab.|
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|Gibt den größten gültigen Index zurück.|
|[CObArray:: InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Fügt ein Element (oder alle Elemente in einem anderen Array) am angegebenen Index ein.|
|[CObArray:: IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|Bestimmt, ob das Array leer ist.|
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Entfernt alle Elemente aus diesem Array.|
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Entfernt ein Element an einem spezifischen Index.|
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|Legt den Wert für einen bestimmten Index fest; Array darf nicht vergrößert werden.|
|[CObArray:: antatgrow](../../mfc/reference/cobarray-class.md#setatgrow)|Legt den Wert für einen bestimmten Index fest; vergrößert das Array bei Bedarf.|
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|Legt die Anzahl der Elemente im Array fest.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CObArray::-Operator&#91;&#93;](../../mfc/reference/cobarray-class.md#operator_at)|Legt das Element am angegebenen Index fest oder ruft es ab.|

## <a name="remarks"></a>Hinweise

`CWordArray`enthält das [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) -Makro, um die Serialisierung und das Absichern Ihrer Elemente zu unterstützen. Wenn ein Array von Wörtern in einem Archiv gespeichert wird, entweder mit einem überladenen einfügeoperator oder mit der [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) -Member-Funktion, wird jedes Element seinerseits serialisiert.

> [!NOTE]
>  Vor dem Verwenden eines Arrays, verwenden Sie `SetSize`, um dessen Größe festzustellen, und weisen dafür Arbeitsspeicher zu. Wenn Sie `SetSize` nicht verwenden, kann das Hinzufügen von Elementen zu Ihrem Array dazu führen, dass es häufig neu zugeordnet und kopiert wird. Häufige Neuzuordnungen und Kopiervorgänge sind ineffizient und können zu einer Fragmentierung des Arbeitsspeichers führen.

Wenn Sie ein Dump einzelner Elemente im Array benötigen, müssen Sie die Tiefe des Sicherungs Kontexts auf 1 oder höher festlegen.

Weitere Informationen zur Verwendung von `CWordArray`finden Sie im Artikel [Sammlungen](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CWordArray`

## <a name="requirements"></a>Anforderungen

**Header:** afxcoll. h

##  <a name="icommandsource_interface"></a>ICommandSource-Schnittstelle

Verwaltet Befehle, die von einem Befehls Quell Objekt an ein Benutzer Steuerelement gesendet werden.

```
interface class ICommandSource
```

### <a name="remarks"></a>Hinweise

Wenn Sie ein Benutzer Steuerelement in einer MFC-Ansicht hosten, leitet die [CWinFormsView-Klasse](../../mfc/reference/cwinformsview-class.md) Befehle und aktualisiert Befehls Benutzeroberflächen-Meldungen an das Benutzer Steuerelement, damit Sie MFC-Befehle (z. b. Frame Menü Elemente und Symbolleisten Schaltflächen) verarbeiten kann. Wenn Sie implementieren, weisen Sie dem Benutzer Steuerelement einen Verweis `ICommandSource` auf das-Objekt zu.

Weitere Informationen finden Sie unter [How to: Fügen Sie dem Windows Forms-Steuer](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) Element das Befehls Routing hinzu, um ein Beispiel für die Verwendung `ICommandTarget`von zu erfahren.

Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzer Steuer Elements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="addcommandhandler"></a>ICommandSource:: AddCommandHandler

Fügt einem Befehls Quell Objekt einen Befehls Handler hinzu.

```
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Parameter

*cmdID*<br/>
Die Befehls-ID.

*cmdHandler*<br/>
Ein Handle für die Befehls Handlermethode.

### <a name="remarks"></a>Hinweise

Diese Methode fügt dem Befehls Quell Objekt den Befehls Handler- *CmdHandler* hinzu und ordnet den Handler *CMDID*zu.

Weitere Informationen finden Sie unter [How to: Fügen Sie dem Windows Forms-Steuer](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) Element das Befehls Routing hinzu, um ein Beispiel für die Verwendung `AddCommandHandler`von zu erfahren.

##  <a name="addcommandrangehandler"></a>ICommandSource:: addcommandrangehandler

Fügt einem Befehls Quell Objekt eine Gruppe von Befehls Handlern hinzu.

```
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Parameter

*cmdIDMin*<br/>
Der Anfangs Index des Befehls-ID-Bereichs.

*cmdIDMax*<br/>
Der Endindex des Befehls-ID-Bereichs.

*cmdHandler*<br/>
Ein Handle für die nachrichtenhandlermethode, der die Befehle zugeordnet werden.

### <a name="remarks"></a>Hinweise

Diese Methode ordnet einen zusammenhängenden Bereich von Befehls-IDs einem einzelnen Nachrichten Handler zu und fügt ihn dem Befehls Quell Objekt hinzu. Diese wird verwendet, um eine Gruppe verwandter Schaltflächen mit einer Methode zu verarbeiten.

##  <a name="addcommandrangeuihandler"></a>ICommandSource:: addcommandrangeuihandler

Fügt einem Befehls Quell Objekt eine Gruppe von Benutzeroberflächen-Befehls Meldungs Handlern hinzu.

```
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Parameter

*cmdIDMin*<br/>
Der Anfangs Index des Befehls-ID-Bereichs.

*cmdIDMax*<br/>
Der Endindex des Befehls-ID-Bereichs.

*cmdHandler*<br/>
Ein Handle für die nachrichtenhandlermethode, der die Befehle zugeordnet werden.

### <a name="remarks"></a>Hinweise

Diese Methode ordnet einen zusammenhängenden Bereich von Befehls-IDs einem einzelnen Benutzeroberflächen-befehlsnachrichten Handler zu und fügt ihn dem Befehls Quell Objekt hinzu. Diese wird verwendet, um eine Gruppe verwandter Schaltflächen mit einer Methode zu verarbeiten.

##  <a name="addcommanduihandler"></a>ICommandSource:: addcommanduihandler

Fügt einem Befehls Quell Objekt einen Benutzeroberflächen-Befehls Meldungs Handler hinzu.

```
void AddCommandUIHandler(
    unsigned int cmdID,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Parameter

*cmdID*<br/>
Die Befehls-ID.

*cmdUIHandler*<br/>
Ein Handle für die Handlermethode der Benutzeroberflächen-Befehls Meldung.

### <a name="remarks"></a>Hinweise

Diese Methode fügt den Befehlszeilen- *CmdHandler* für die Benutzeroberflächen Befehle zum Befehls Quell Objekt hinzu und ordnet den Handler *CMDID*zu.

##  <a name="postcommand"></a>ICommandSource::P ostcommand

Sendet eine Nachricht, ohne darauf zu warten, dass Sie verarbeitet wird.

```
void PostCommand(unsigned int command);
```

### <a name="parameters"></a>Parameter

*command*<br/>
Die Befehls-ID der Nachricht, die gepostet werden soll.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die Nachricht, die der durch den *Befehl*angegebenen ID zugeordnet ist, asynchron. [CWnd::P ostmessage](../../mfc/reference/cwnd-class.md#postmessage) wird aufgerufen, um die Nachricht in der Nachrichten Warteschlange des Fensters zu platzieren, und dann wird zurückgegeben, ohne darauf zu warten, dass das entsprechende Fenster die Nachricht verarbeitet.

##  <a name="removecommandhandler"></a>ICommandSource:: removecommandhandler

Entfernt einen Befehls Handler aus einem Befehls Quell Objekt.

```
void RemoveCommandHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Parameter

*cmdID*<br/>
Die Befehls-ID.

### <a name="remarks"></a>Hinweise

Diese Methode entfernt den Befehls Handler, der *CMDID* zugeordnet ist, aus dem Befehls Quell Objekt.

##  <a name="removecommandrangehandler"></a>ICommandSource:: removecommandrangehandler

Entfernt eine Gruppe von Befehls Handlern aus einem Befehls Quell Objekt.

```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Parameter

*cmdIDMin*<br/>
Der Anfangs Index des Befehls-ID-Bereichs.

*cmdIDMax*<br/>
Der Endindex des Befehls-ID-Bereichs.

### <a name="remarks"></a>Hinweise

Diese Methode entfernt eine Gruppe von Meldungs Handlern, die den von *cmdidmin* und *cmdidmax*angegebenen Befehls-IDs zugeordnet sind, aus dem Befehls Quell Objekt.

##  <a name="removecommandrangeuihandler"></a>ICommandSource:: removecommandrangeuihandler

Entfernt eine Gruppe von befehlsnachrichten Handlern für Benutzeroberflächen aus einem Befehls Quell Objekt.

```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Parameter

*cmdIDMin*<br/>
Der Anfangs Index des Befehls-ID-Bereichs.

*cmdIDMax*<br/>
Der Endindex des Befehls-ID-Bereichs.

### <a name="remarks"></a>Hinweise

Diese Methode entfernt eine Gruppe von Benutzeroberflächen-Befehls Meldungs Handlern, die den von *cmdidmin* und *cmdidmax*angegebenen Befehls-IDs zugeordnet sind, aus dem Befehls Quell Objekt.

##  <a name="removecommanduihandler"></a>ICommandSource:: removecommanduihandler

Entfernt einen Benutzeroberflächen-befehlsnachrichten Handler aus einem Befehls Quell Objekt.

```
void RemoveCommandUIHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Parameter

*cmdID*<br/>
Die Befehls-ID.

### <a name="remarks"></a>Hinweise

Mit dieser Methode wird der Benutzeroberflächen-Befehls Meldungs Handler, der *CMDID* zugeordnet ist, aus dem Befehls Quell Objekt entfernt.

##  <a name="sendcommand"></a>ICommandSource:: Send Command

Sendet eine Nachricht und wartet darauf, dass Sie vor der Rückgabe verarbeitet wird.

```
void SendCommand(unsigned int command);
```

### <a name="parameters"></a>Parameter

*command*<br/>
Die Befehls-ID der zu sendenden Nachricht.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die Nachricht, die der durch den *Befehl*angegebenen ID zugeordnet ist, synchron. [CWnd:: SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) wird aufgerufen, um die Nachricht in der Meldungs Warteschlange des Fensters zu platzieren, und wartet, bis die Fenster Prozedur die Nachricht vor der Rückgabe verarbeitet hat.

##  <a name="icommandtarget_interface"></a>ICommandTarget-Schnittstelle

Stellt ein Benutzer Steuerelement mit einer Schnittstelle zum Empfangen von Befehlen von einem Befehls Quell Objekt bereit.

```
interface class ICommandTarget
```

### <a name="remarks"></a>Hinweise

Wenn Sie ein Benutzer Steuerelement in einer MFC-Ansicht hosten, leitet [CWinFormsView](../../mfc/reference/cwinformsview-class.md) Befehle und Aktualisierungs Befehls-UI-Meldungen an das Benutzer Steuerelement weiter, damit es MFC-Befehle (z. b. Frame Menü Elemente und Symbolleisten Schaltflächen) verarbeiten kann. Wenn Sie `ICommandTarget`implementieren, weisen Sie dem Benutzer Steuerelement einen Verweis auf das-Objekt zu.

Weitere Informationen finden Sie unter [How to: Fügen Sie dem Windows Forms-Steuer](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) Element das Befehls Routing hinzu, um ein Beispiel für die Verwendung `ICommandTarget`von zu erfahren.

Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzer Steuer Elements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="initialize"></a>ICommandTarget:: Initialize

Initialisiert das Befehls Zielobjekt.

```
void Initialize(ICommandSource^ cmdSource);
```

### <a name="parameters"></a>Parameter

*cmdSource*<br/>
Ein Handle für das Befehls Quell Objekt.

### <a name="remarks"></a>Hinweise

Wenn Sie ein Benutzer Steuerelement in einer MFC-Ansicht hosten, leitet [CWinFormsView](../../mfc/reference/cwinformsview-class.md) Befehle und aktualisiert Befehls Benutzeroberflächen Meldungen an das Benutzer Steuerelement, damit MFC-Befehle verarbeitet werden können.

Diese Methode initialisiert das Befehls Zielobjekt und ordnet es der angegebenen *cmdsource*des Befehls Quell Objekts zu. Er sollte in der Implementierung der Benutzer Steuerelement Klasse aufgerufen werden. Bei der Initialisierung sollten Sie Befehls Handler beim Befehls Quell Objekt registrieren, indem Sie [ICommandSource:: AddCommandHandler](../../mfc/reference/icommandsource-interface.md) in der `Initialize` -Implementierung aufrufen. Weitere Informationen finden Sie unter [How to: Fügen Sie dem Windows Forms-Steuer](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) Element das Befehls Routing hinzu, um ein Beispiel dafür zu erfahren, wie Sie hierfür verwenden `Initialize` können.

##  <a name="icommandui_interface"></a>Icommandui-Schnittstelle

Verwaltet Befehle der Benutzeroberfläche.

```
interface class ICommandUI
```

### <a name="remarks"></a>Hinweise

Diese Schnittstelle stellt Methoden und Eigenschaften bereit, mit denen Benutzeroberflächen Befehle verwaltet werden. `ICommandUI`ähnelt der [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md), mit der `ICommandUI` Ausnahme, dass für MFC-Anwendungen verwendet wird, die mit .NET-Komponenten zusammenarbeiten.

`ICommandUI`wird innerhalb eines `ON_UPDATE_COMMAND_UI` -Handlers in einer von abgeleiteten Klasse verwendet. Wenn ein Benutzer einer Anwendung ein Menü aktiviert (auswählt oder klickt), wird jedes Menü Element als aktiviert oder deaktiviert angezeigt. Das Ziel der einzelnen Menübefehle bietet diese Informationen durch Implementieren eines `ON_UPDATE_COMMAND_UI` -Handlers. Verwenden Sie für jedes Befehls Benutzeroberflächen Objekt in der Anwendung den Klassen- [Assistenten](mfc-class-wizard.md) oder das **Eigenschaften** Fenster (in **Klassenansicht**), um einen Meldungs Zuordnungs Eintrag und einen Funktionsprototyp für jeden Handler zu erstellen.

Weitere Informationen zur Verwendung der `ICommandUI` -Schnittstelle im Befehls Routing finden [Sie unter Gewusst wie: Fügen Sie dem Windows Forms-Steuer](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)Element das Befehls Routing hinzu.

Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzer Steuer Elements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

Weitere Informationen zur Verwaltung von Benutzeroberflächen Befehlen in MFC finden Sie unter [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md).

##  <a name="check"></a>Icommandui:: Check

Legt das Element der Benutzeroberfläche für diesen Befehl auf den entsprechenden Prüf Zustand fest.

```
property UICheckState Check;
```

### <a name="remarks"></a>Hinweise

Mit dieser Eigenschaft wird das Benutzeroberflächen Element für diesen Befehl auf den entsprechenden Prüf Zustand festgelegt. Legen `Check` Sie auf die folgenden Werte fest:

|Begriff|Definition|
|----------|----------------|
|0|Deaktivieren Sie|
|1|Azure Functions|
|2|Unbestimmtes festlegen|

##  <a name="continuerouting"></a>Icommandui:: continuerouting

Weist den Befehls Routing Mechanismus an, das Weiterleiten der aktuellen Nachricht an die Kette von Handlern weiterzuleiten.

```
void ContinueRouting();
```

### <a name="remarks"></a>Hinweise

Dabei handelt es sich um eine erweiterte Member-Funktion, die in Verbindung mit einem [ON_COMMAND_EX](message-map-macros-mfc.md#on_command_ex) -Handler verwendet werden sollte, der false zurückgibt. Weitere Informationen finden Sie unter Technical Note [TN006: Meldungs](../../mfc/tn006-message-maps.md)Zuordnungen.

##  <a name="enabled"></a>Icommandui:: aktiviert

Aktiviert oder deaktiviert das Benutzeroberflächen Element für diesen Befehl.

```
property bool Enabled;
```

### <a name="remarks"></a>Hinweise

Diese Eigenschaft aktiviert oder deaktiviert das Benutzeroberflächen Element für diesen Befehl. Auf `Enabled` true festgelegt, um das Element zu aktivieren, false, um es zu deaktivieren.

##  <a name="id"></a>Icommandui:: ID

Ruft die ID des Benutzeroberflächen Objekts ab, das durch `ICommandUI` das-Objekt dargestellt wird.

```
property unsigned int ID;
```

### <a name="remarks"></a>Hinweise

Diese Eigenschaft ruft die ID (ein Handle) des Menü Elements, der Symbolleisten-Schaltfläche oder eines anderen Benutzeroberflächen Objekts `ICommandUI` ab, das durch das-Objekt dargestellt wird.

##  <a name="index"></a>Icommandui:: Index

Ruft den Index des Benutzeroberflächen Objekts ab, das durch `ICommandUI` das-Objekt dargestellt wird.

```
property unsigned int Index;
```

### <a name="remarks"></a>Hinweise

Diese Eigenschaft ruft den Index (ein Handle) des Menü Elements, der Symbolleisten-Schaltfläche oder eines anderen Benutzeroberflächen Objekts `ICommandUI` ab, das durch das-Objekt dargestellt wird.

##  <a name="radio"></a>Icommandui:: Radio

Legt das Element der Benutzeroberfläche für diesen Befehl auf den entsprechenden Prüf Zustand fest.

```
property bool Radio;
```

### <a name="remarks"></a>Hinweise

Mit dieser Eigenschaft wird das Benutzeroberflächen Element für diesen Befehl auf den entsprechenden Prüf Zustand festgelegt. Auf `Radio` true festgelegt, um das Element zu aktivieren; andernfalls false.

##  <a name="text"></a>Icommandui:: Text

Legt den Text des Benutzeroberflächen Elements für diesen Befehl fest.

```
property String^ Text;
```

### <a name="remarks"></a>Hinweise

Diese Eigenschaft legt den Text des Benutzeroberflächen Elements für diesen Befehl fest. Legen `Text` Sie auf ein Textzeichen folgen Handle fest.

##  <a name="iview_interface"></a>IView-Schnittstelle

Implementiert mehrere Methoden, die [CWinFormsView](../../mfc/reference/cwinformsview-class.md) verwendet, um Ansichts Benachrichtigungen an ein verwaltetes Steuerelement zu senden.

```
interface class IView
```

### <a name="remarks"></a>Hinweise

`IView`implementiert verschiedene Methoden, `CWinFormsView` mit denen allgemeine Ansichts Benachrichtigungen an ein gehosteter verwaltetes Steuerelement weitergeleitet werden. Dabei handelt es sich um [OnInitialUpdate](../../mfc/reference/iview-interface.md), [OnUpdate](../../mfc/reference/iview-interface.md) und [OnActivateView](../../mfc/reference/iview-interface.md).

`IView`ähnelt [CView](../../mfc/reference/cview-class.md), wird jedoch nur mit verwalteten Sichten und Steuerelementen verwendet.

Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzer Steuer Elements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="onactivateview"></a>IView:: OnActivateView

Wird von MFC aufgerufen, wenn eine Ansicht aktiviert oder deaktiviert wird.

```
void OnActivateView(bool activate);
```

### <a name="parameters"></a>Parameter

*Aktivieren*<br/>
Gibt an, ob die Ansicht aktiviert oder deaktiviert wird.

##  <a name="oninitialupdate"></a>IView:: OnInitialUpdate

Wird von Framework aufgerufen, nachdem die Ansicht zum ersten Mal an das Dokument angefügt wurde, aber bevor die Ansicht anfänglich angezeigt wird.

```
void OnInitialUpdate();
```

##  <a name="onupdate"></a>IView:: OnUpdate

Wird von MFC aufgerufen, nachdem das Dokument der Ansicht geändert wurde.

```
void OnUpdate();
```

### <a name="remarks"></a>Hinweise

Diese Funktion ermöglicht der Ansicht, Ihre Anzeige zu aktualisieren, um Änderungen widerzuspiegeln.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel Sammlung](../../overview/visual-cpp-samples.md)<br/>
[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
