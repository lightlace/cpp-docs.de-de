---
title: CMFCRibbonApplicationButton-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::SetImage
helpviewer_keywords:
- CMFCRibbonApplicationButton [MFC], CMFCRibbonApplicationButton
- CMFCRibbonApplicationButton [MFC], SetImage
ms.assetid: beb81757-fabd-4641-9130-876ba8505b78
ms.openlocfilehash: d1dc8ef6e801623aa96cb4b47936413cd17f24f0
ms.sourcegitcommit: c3bf94210bdb73be80527166264d49e33784152c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2019
ms.locfileid: "68821237"
---
# <a name="cmfcribbonapplicationbutton-class"></a>CMFCRibbonApplicationButton-Klasse

Implementiert eine spezielle Schaltfläche in der oberen linken Ecke des Anwendungsfensters. Wenn sie angeklickt wird, öffnet die Schaltfläche ein Menü, das normalerweise allgemeine **Datei** -Befehle wie **Öffnen**, **Speichern**und **Beenden**enthält.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonApplicationButton : public CMFCRibbonButton
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonApplicationButton::CMFCRibbonApplicationButton](#cmfcribbonapplicationbutton)|Erstellt und initialisiert ein `CMFCRibbonApplicationButton`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|`CMFCRibbonApplicationButton::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|`CMFCRibbonApplicationButton::GetThisClass`|Wird vom Framework verwendet, um einen Zeiger auf das [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|
|[CMFCRibbonApplicationButton::SetImage](#setimage)|Weist der Menüband-Anwendungs Schaltfläche ein Bild zu.|

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung verschiedener Methoden in der `CMFCRibbonApplicationButton` -Klasse. Das Beispiel zeigt, wie der Anwendungs Schaltfläche ein Bild zugewiesen wird und wie die QuickInfo festgelegt wird. Dieser Codeausschnitt ist Teil des [Draw Client-Beispiels](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#4](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_1.h)]
[!code-cpp[NVC_MFC_DrawClient#5](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxribbonbar. h

##  <a name="cmfcribbonapplicationbutton"></a>CMFCRibbonApplicationButton:: CMFCRibbonApplicationButton

Erstellt und initialisiert ein [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md) -Objekt.

```
CMFCRibbonApplicationButton();
CMFCRibbonApplicationButton(UINT uiBmpResID);
CMFCRibbonApplicationButton(HBITMAP hBmp);
```

### <a name="parameters"></a>Parameter

*uiBmpResID*<br/>
Die Ressourcen-ID des Bilds, das auf der Anwendungs Schaltfläche angezeigt werden soll.

*hBmp*<br/>
Ein Handle für eine Bitmap, die auf der Anwendungs Schaltfläche angezeigt werden soll.

### <a name="remarks"></a>Hinweise

Die Schaltfläche für die Menüband-Anwendung ist eine spezielle Schaltfläche, die sich in der oberen linken Ecke des Anwendungsfensters befindet. Wenn ein Benutzer auf diese Schaltfläche klickt, öffnet die Anwendung ein Menü, das normalerweise allgemeine **Datei** Befehle wie **Öffnen**, **Speichern**und **Beenden**enthält.

##  <a name="setimage"></a>CMFCRibbonApplicationButton:: stimage

Weist der Anwendungs Schaltfläche ein Bild zu.

```
void SetImage(UINT uiBmpResID);
void SetImage(HBITMAP hBmp);
```

### <a name="parameters"></a>Parameter

*uiBmpResID*<br/>
in Die Ressourcen-ID des Bilds, das auf der Anwendungs Schaltfläche angezeigt werden soll.

*hBmp*<br/>
in Ein Handle für eine Bitmap, die auf der Anwendungs Schaltfläche angezeigt werden soll.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um ein neues Bild der Menüband-Anwendungs Schaltfläche zuzuweisen, nachdem Sie die Schaltfläche erstellt haben. Die Anwendungs Schaltfläche befindet sich in der oberen linken Ecke des Anwendungsfensters.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton-Klasse](../../mfc/reference/cmfcribbonbutton-class.md)
