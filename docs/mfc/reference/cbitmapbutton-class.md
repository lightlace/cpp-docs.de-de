---
title: CBitmapButton-Klasse
ms.date: 11/04/2016
f1_keywords:
- CBitmapButton
- AFXEXT/CBitmapButton
- AFXEXT/CBitmapButton::CBitmapButton
- AFXEXT/CBitmapButton::AutoLoad
- AFXEXT/CBitmapButton::LoadBitmaps
- AFXEXT/CBitmapButton::SizeToContent
helpviewer_keywords:
- CBitmapButton [MFC], CBitmapButton
- CBitmapButton [MFC], AutoLoad
- CBitmapButton [MFC], LoadBitmaps
- CBitmapButton [MFC], SizeToContent
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
ms.openlocfilehash: 6bff87cd7648e1e5f4e0391a0a7fc1a1455a51f0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599653"
---
# <a name="cbitmapbutton-class"></a>CBitmapButton-Klasse

Erstellt Pushbutton-Steuerelemente, die mit Bitmapbildern statt mit Text bezeichnet sind.

## <a name="syntax"></a>Syntax

```
class CBitmapButton : public CButton
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CBitmapButton::CBitmapButton](#cbitmapbutton)|Erstellt ein `CBitmapButton`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CBitmapButton:: AutoLoad](#autoload)|Ordnet eine Schaltfläche in einem Dialogfeld ein Objekt der `CBitmapButton` -Klasse, lädt die Bitmap(s) anhand des Namens und die Größe der Schaltfläche entsprechend die Bitmap.|
|[CBitmapButton::LoadBitmaps](#loadbitmaps)|Laden eine oder mehrere benannte Bitmapressourcen aus der Ressourcendatei der Anwendung und Anfügen von Bitmaps auf das Objekt initialisiert das Objekt.|
|[CBitmapButton::SizeToContent](#sizetocontent)|Die Größe der Schaltfläche zur Aufnahme die Bitmap.|

## <a name="remarks"></a>Hinweise

`CBitmapButton` -Objekte enthalten, bis zu vier Bitmaps, die Images für die unterschiedlichen Zustände enthalten, eine Schaltfläche kann davon ausgehen: Sie (oder normal), nach unten (oder ausgewählte) mit Fokus, und deaktiviert. Nur die ersten Bitmap ist erforderlich. die anderen sind optional.

Bitmap-Button-Images enthalten den Rahmen um das Bild als auch auf das Bild selbst. Der Rahmen spielt in der Regel eine den Status der Schaltfläche anzeigen. Beispielsweise ist die Bitmap für den Status der Fokus in der Regel wie die für den gedrückten Zustand jedoch mit einer gestrichelten Rechteck Inset über den Rahmen oder eine dicke durchgehende Linie an der Grenze. Die Bitmap ähnelt für die deaktivierten, in der Regel Zustand der für den gedrückten Zustand jedoch niedriger Kontrast (z. B. eine Auswahl Menü abgeblendet oder abgeblendet weist).

Diese Bitmaps können von beliebiger Größe sein, jedoch werden alle behandelt, als wären sie die gleiche Größe wie die Bitmap für den gedrückten Zustand.

Verschiedene Anwendungen erfordern verschiedene Kombinationen von Bitmapbildern:

|Nach oben|Nach unten|Focused (Mit Fokus)|Deaktiviert|Application|
|--------|----------|-------------|--------------|-----------------|
|×||||Bitmap|
|×|×|||Klicken, ohne WS_TABSTOP-Stil|
|×|×|×|×|Schaltfläche mit allen Zuständen|
|×|×|×||Schaltfläche mit WS_TABSTOP-Stil|

Wenn Sie ein Bitmap-Schaltflächen-Steuerelement zu erstellen, legen Sie den BS_OWNERDRAW-Stil, um anzugeben, dass die Schaltfläche mit der Ownerdrawn. Dies bewirkt, dass Windows die WM_MEASUREITEM und WM_DRAWITEM Nachrichten für die Schaltfläche "; Das Framework verarbeitet diese Nachrichten und die Darstellung der Schaltfläche für Sie verwaltet.

### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>Erstellen Sie ein Bitmap-Schaltflächen-Steuerelement im Clientbereich eines Fensters

1. Erstellen Sie eine bis vier Bitmapbilder für die Schaltfläche.

1. Erstellen der [CBitmapButton](#cbitmapbutton) Objekt.

1. Rufen Sie die [erstellen](../../mfc/reference/cbutton-class.md#create) -Funktion zum Erstellen des Windows-Schaltflächensteuerelements und fügen Sie ihn auf die `CBitmapButton` Objekt.

1. Rufen Sie die [LoadBitmaps](#loadbitmaps) Memberfunktion, um die Bitmapressourcen geladen werden, nachdem die Schaltfläche "Bitmap" erstellt wurde.

### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>Um ein Bitmap-Schaltflächen-Steuerelement in einem Dialogfeld einzuschließen.

1. Erstellen Sie eine bis vier Bitmapbilder für die Schaltfläche.

1. Erstellen Sie eine Dialogfeldvorlage, mit einem Ownerdrawn-Schaltfläche positioniert wird, möchten Sie die Schaltfläche "Bitmap". Die Größe der Schaltfläche in der Vorlage spielt keine Rolle.

1. Die Beschriftung der Schaltfläche auf einen Wert wie z. B. "MYIMAGE" festgelegt, und definieren Sie ein Symbol für die Schaltfläche wie z. B. IDC_MYIMAGE.

1. In Ihrer Anwendung Ressourcenskript geben jedes der Images erstellte, die durch Anfügen einer der Buchstaben "U", "D", "F", ID für die Schaltfläche erstellt, oder "X" (für sich nach unten konzentriert, und deaktiviert) auf die Zeichenfolge für die Beschriftung der Schaltfläche in Schritt 3. Für die Beschriftung der Schaltfläche "MYIMAGE", z. B. die IDs wäre "MYIMAGEU", "MYIMAGED", "MYIMAGEF" und "MYIMAGEX." Sie **müssen** die ID des Ihre Bitmaps in doppelten Anführungszeichen angeben. Andernfalls wird der Ressourcen-Editor weist eine ganze Zahl auf die Ressource, und MFC schlägt fehl, wenn das Bild geladen.

1. In Ihrer Anwendung Dialogfeld-Klasse (abgeleitet `CDialog`), Hinzufügen einer `CBitmapButton` Member-Objekt.

1. In der `CDialog` des Objekts [OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog) routinemäßig ausgeführt werden, der Aufruf der `CBitmapButton` des Objekts [AutoLoad](#autoload) Funktion mit als Parameter der Schaltfläche die Steuerelement-ID und die `CDialog` des Objekts **dies** Zeiger.

Sollten Sie Windows-benachrichtigungsmeldungen, z. B. BN_CLICKED, Behandeln von ein Bitmap-Schaltflächen-Steuerelement an sein übergeordnetes Element gesendet (in der Regel eine abgeleitete Klasse `CDialog`), zum Hinzufügen der `CDialog`-abgeleitete Objekt ein meldungszuordnung Eintrag und die Meldungshandler Element die Funktion für jede Nachricht. Die Benachrichtigungen gesendet werden, indem eine `CBitmapButton` Objekt sind identisch mit denen per eine [CButton](../../mfc/reference/cbutton-class.md) Objekt.

Die Klasse [CToolBar](../../mfc/reference/ctoolbar-class.md) verwendet einen anderen Ansatz zu Bitmapschaltflächen.

Weitere Informationen zu `CBitmapButton`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

`CBitmapButton`

## <a name="requirements"></a>Anforderungen

**Header:** afxext.h

##  <a name="autoload"></a>  CBitmapButton:: AutoLoad

Ordnet eine Schaltfläche in einem Dialogfeld ein Objekt der `CBitmapButton` -Klasse, lädt die Bitmap(s) anhand des Namens und die Größe der Schaltfläche entsprechend die Bitmap.

```
BOOL AutoLoad(
    UINT nID,
    CWnd* pParent);
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Die Schaltfläche "-Steuerelement-ID.

*pParent*<br/>
Zeiger auf das Objekt, das die Schaltfläche besitzt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Verwenden der `AutoLoad` Funktion, um ein Ownerdrawn-Schaltfläche in einem Dialogfeld als Bitmapschaltfläche zu initialisieren. Anweisungen zur Verwendung dieser Funktion sind in den Hinweisen für die `CBitmapButton` Klasse.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCControlLadenDialog#75](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]

##  <a name="cbitmapbutton"></a>  CBitmapButton::CBitmapButton

Erstellt ein `CBitmapButton`-Objekt.

```
CBitmapButton();
```

### <a name="remarks"></a>Hinweise

Nach dem Erstellen der C++ `CBitmapButton` Objekt, rufen Sie [CButton::Create](../../mfc/reference/cbutton-class.md#create) erstellen das Windows-Schaltflächensteuerelement und fügen Sie ihn auf die `CBitmapButton` Objekt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCControlLadenDialog#57](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]

##  <a name="loadbitmaps"></a>  CBitmapButton::LoadBitmaps

Verwenden Sie diese Funktion, wenn beim Laden von Bitmapbildern identifiziert nach Ressourcennamen oder ID-Nummern werden, oder wenn Sie nicht verwenden können sollen die `AutoLoad` funktionieren, weil z. B. Sie eine Bitmapschaltfläche erstellen, die nicht Teil eines Dialogfelds ist.

```
BOOL LoadBitmaps(
    LPCTSTR lpszBitmapResource,
    LPCTSTR lpszBitmapResourceSel = NULL,
    LPCTSTR lpszBitmapResourceFocus = NULL,
    LPCTSTR lpszBitmapResourceDisabled = NULL);

BOOL LoadBitmaps(
    UINT nIDBitmapResource,
    UINT nIDBitmapResourceSel = 0,
    UINT nIDBitmapResourceFocus = 0,
    UINT nIDBitmapResourceDisabled = 0);
```

### <a name="parameters"></a>Parameter

*lpszBitmapResource*<br/>
Verweist auf die Null-terminierte Zeichenfolge mit dem Namen der Bitmap für eine Bitmapschaltfläche Normal oder "fehlerfrei". Erforderlich.

*lpszBitmapResourceSel*<br/>
Zeigt, der Null-terminierte Zeichenfolge mit dem Namen der Bitmap für die Auswahl einer Bitmapschaltfläche, die bzw. "Zustand" ausgefallen"". NULL kann sein.

*lpszBitmapResourceFocus*<br/>
Verweist auf die Null-terminierte Zeichenfolge mit dem Namen der Bitmap für einer Bitmapschaltfläche mit Fokus Zustand. NULL kann sein.

*lpszBitmapResourceDisabled*<br/>
Status "deaktiviert" verweist auf die Null-terminierte Zeichenfolge, die den Namen der Bitmap für einer Bitmapschaltfläche enthält. NULL kann sein.

*nIDBitmapResource*<br/>
Gibt an, die Ressourcen-ID-Nummer der Bitmapressource für eine Bitmapschaltfläche Normal oder "fehlerfrei". Erforderlich.

*nIDBitmapResourceSel*<br/>
Gibt die Ressourcen-ID-Nummer der Bitmapressource an, für die Auswahl einer Bitmapschaltfläche, die oder "Zustand" ausgefallen"". 0 kann sein.

*nIDBitmapResourceFocus*<br/>
Gibt an, die Ressourcen-ID-Nummer der Bitmapressource für den Zustand einer Bitmapschaltfläche mit Fokus. 0 kann sein.

*nIDBitmapResourceDisabled*<br/>
Gibt die Ressourcen-ID-Nummer der Bitmapressource für deaktivierten Zustand einer Bitmapschaltfläche eine an. 0 kann sein.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCControlLadenDialog#58](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]

##  <a name="sizetocontent"></a>  CBitmapButton::SizeToContent

Rufen Sie diese Funktion zum Ändern der Größe einer Bitmapschaltfläche, um die Größe der Bitmap.

```
void SizeToContent();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCControlLadenDialog#59](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel CTRLTEST](../../visual-cpp-samples.md)<br/>
[CButton-Klasse](../../mfc/reference/cbutton-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)

