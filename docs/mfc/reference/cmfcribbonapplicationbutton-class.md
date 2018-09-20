---
title: CMFCRibbonApplicationButton-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::SetImage
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonApplicationButton [MFC], CMFCRibbonApplicationButton
- CMFCRibbonApplicationButton [MFC], SetImage
ms.assetid: beb81757-fabd-4641-9130-876ba8505b78
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b82e0da2ac080ea65807b92f7eab549fe3301bf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393801"
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

Im folgende Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCRibbonApplicationButton` Klasse. Das Beispiel zeigt, wie Sie die Schaltfläche "Application" ein Bild zuzuweisen, und die QuickInfo festlegen. Dieser Codeausschnitt ist Teil des [Draw Client-Beispiels](../../visual-cpp-samples.md).

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
