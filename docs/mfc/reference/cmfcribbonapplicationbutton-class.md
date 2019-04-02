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
ms.openlocfilehash: 01b6937ee597766922597fda5664c78f75be6b67
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58772162"
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
|`CMFCRibbonApplicationButton::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|
|[CMFCRibbonApplicationButton::SetImage](#setimage)|Weist ein Bild der Schaltfläche des Menübands-Anwendung.|

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung verschiedener Methoden in der `CMFCRibbonApplicationButton` -Klasse. Das Beispiel zeigt, wie Sie die Schaltfläche "Application" ein Bild zuzuweisen, und die QuickInfo festlegen. Dieser Codeausschnitt ist Teil des [Draw Client-Beispiels](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#4](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_1.h)]
[!code-cpp[NVC_MFC_DrawClient#5](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxRibbonBar.h

##  <a name="cmfcribbonapplicationbutton"></a>  CMFCRibbonApplicationButton::CMFCRibbonApplicationButton

Erstellt und initialisiert ein [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md) Objekt.

```
CMFCRibbonApplicationButton();
CMFCRibbonApplicationButton(UINT uiBmpResID);
  CMFCRibbonApplicationButton(HBITMAP hBmp);
```

### <a name="parameters"></a>Parameter

*uiBmpResID*<br/>
Die Ressourcen-ID des Images, die auf die Schaltfläche "Anwendung" angezeigt.

*hBmp*<br/>
Ein Handle für eine Bitmap, die auf die Schaltfläche "Anwendung" angezeigt.

### <a name="remarks"></a>Hinweise

Die Menübandschaltfläche für die Anwendung ist eine spezielle Schaltfläche, die in der oberen linken Ecke des Anwendungsfensters befindet. Wenn ein Benutzer diese Schaltfläche klickt, wird die Anwendung öffnet ein Menü mit in der Regel häufig **Datei** Befehle wie **öffnen**, **speichern**, und **beenden**.

##  <a name="setimage"></a>  CMFCRibbonApplicationButton::SetImage

Weist ein Bild an die Anwendungsschaltfläche an.

```
void SetImage(UINT uiBmpResID);
void SetImage(HBITMAP hBmp);
```

### <a name="parameters"></a>Parameter

*uiBmpResID*<br/>
[in] Die Ressourcen-ID des Images, die auf die Schaltfläche "Anwendung" angezeigt.

*hBmp*<br/>
[in] Ein Handle für eine Bitmap, die auf die Schaltfläche "Anwendung" angezeigt.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode die Menübandschaltfläche für die Anwendung nach der Erstellung der Schaltfläche ein neues Abbild zuweisen. Die Schaltfläche "Anwendung" befindet sich in der oberen linken Ecke des Anwendungsfensters.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton-Klasse](../../mfc/reference/cmfcribbonbutton-class.md)
