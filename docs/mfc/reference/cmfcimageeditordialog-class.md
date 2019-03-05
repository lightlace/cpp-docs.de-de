---
title: CMFCImageEditorDialog-Klasse
ms.date: 11/19/2018
f1_keywords:
- CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog::CMFCImageEditorDialog
helpviewer_keywords:
- CMFCImageEditorDialog [MFC], CMFCImageEditorDialog
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
ms.openlocfilehash: 57b1df49616967841a433a36a504beed0b900cde
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57278534"
---
# <a name="cmfcimageeditordialog-class"></a>CMFCImageEditorDialog-Klasse

Die `CMFCImageEditorDialog` Klasse unterstützt ein bildbearbeitungs-Dialogfeld.

## <a name="syntax"></a>Syntax

```
class CMFCImageEditorDialog : public CDialogEx
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCImageEditorDialog::CMFCImageEditorDialog](#cmfcimageeditordialog)|Erstellt ein `CMFCImageEditorDialog`-Objekt.|

## <a name="remarks"></a>Hinweise

Die `CMFCImageEditorDialog` -Klasse stellt ein Dialogfeld, das enthält:

- Ein Bildbereich, mit denen Sie einzelne Pixel in einem Bild zu ändern.

- Zeichnen die Tools, um die Pixel im Bildbereich zu ändern.

- Eine Farbpalette an die Farbe, die von den Zeichentools verwendet wird.

- Einen Vorschaubereich, in dem die Auswirkungen der Bearbeitung angezeigt.

Die folgende Abbildung zeigt ein Bild-Editor im Dialogfeld an.

![CMFCImageEditorDialog-Dialogfeld](../../mfc/reference/media/imageedit.png "CMFCImageEditorDialog-Dialogfeld")

Eine Möglichkeit zur Verwendung einer `CMFCImageEditorDialog` Objekt ist das Übergeben einer `CBitmap` Bild, das bearbeitet werden. Ein großes Bild kann nicht erstellt werden, da der Bereich für die bildbearbeitung verfügt über nur eine begrenzte Größe und die logische Pixelgröße angepasst wird, um den Bereich passt. Rufen Sie die `DoModal` Methode, um ein modales Dialogfeld starten.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afximageeditordialog.h

##  <a name="cmfcimageeditordialog"></a>  CMFCImageEditorDialog::CMFCImageEditorDialog

Erstellt ein `CMFCImageEditorDialog`-Objekt.

```
CMFCImageEditorDialog(
    CBitmap* pBitmap,
    CWnd* pParent=NULL,
    int nBitsPixel=-1);
```

### <a name="parameters"></a>Parameter

*pBitmap*<br/>
Zeiger auf ein Bild.

*pParent*<br/>
Zeiger auf das übergeordnete Fenster das aktuelle Bild-Editor-Dialogfeld.

*nBitsPixel*<br/>
Die Anzahl der Bits verwendet, um die Farbe der ein einzelnes Pixel darzustellen, die auch als Farbtiefe bezeichnet wird.  Wenn die *nBitsPixel* Parameter ist 1, die Farbtiefe stammt aus dem Image gemäß den *pBitmap* Parameter. Der Standardwert ist -1.

### <a name="return-value"></a>Rückgabewert

Um ein Bild ändern möchten, übergeben Sie einen Image-Zeiger auf die `CMFCImageEditorDialog` Konstruktor. Rufen Sie dann die `DoModal` Methode, um ein modales Dialogfeld zu öffnen. Wenn die `DoModal` Methode zurückgegeben wird, enthält das Bitmuster des neuen Images.

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zum Erstellen eines Objekts von der `CMFCImageEditorDialog` Klasse. In diesem Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#8](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]
[!code-cpp[NVC_MFC_NewControls#40](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)
