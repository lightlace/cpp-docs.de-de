---
title: CMFCTabToolTipInfo-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCTabToolTipInfo
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabToolTipInfo struct
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21e612615110370922d71e1acaebcda56b2e692e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46435453"
---
# <a name="cmfctabtooltipinfo-structure"></a>CMFCTabToolTipInfo-Struktur

Diese Struktur enthält Informationen über die MDI-Registerkarte, der der Benutzer zeigt.

## <a name="syntax"></a>Syntax

```
struct CMFCTabToolTipInfo
```

## <a name="members"></a>Member

### <a name="data-members"></a>Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CMFCTabToolTipInfo::m_nTabIndex](#m_ntabindex)|Gibt den Index des Registerkarten-Steuerelements.|
|[CMFCTabToolTipInfo::m_pTabWnd](#m_ptabwnd)|Ein Zeiger auf das Registerkarten-Steuerelement.|
|[CMFCTabToolTipInfo::m_strText](#m_strtext)|Der QuickInfo-Text.|

## <a name="remarks"></a>Hinweise

Ein Zeiger auf eine `CMFCTabToolTipInfo` Struktur als Parameter der Nachricht AFX_WM_ON_GET_TAB_TOOLTIP übergeben wird. Diese Meldung wird generiert, wenn MDI-Registerkarten aktiviert sind, und Benutzer auf ein Registerkarten-Steuerelement zeigen.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt wie `CMFCTabToolTipInfo` werden in der [MDITabsDemo-Beispiel: MFC-im Registerkartenformat MDI-Anwendung](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CMFCTabToolTipInfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxbasetabctrl.h

##  <a name="m_ntabindex"></a>  CMFCTabToolTipInfo::m_nTabIndex

Gibt den Index des Registerkarten-Steuerelements.

```
int m_nTabIndex;
```

### <a name="remarks"></a>Hinweise

Der Index der Registerkarte für die der Benutzer zeigt.

### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt wie `m_nTabIndex` werden in der [MDITabsDemo-Beispiel: MFC-im Registerkartenformat MDI-Anwendung](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

##  <a name="m_ptabwnd"></a>  CMFCTabToolTipInfo::m_pTabWnd

Ein Zeiger auf das Registerkarten-Steuerelement.

```
CMFCBaseTabCtrl* m_pTabWnd;
```

### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt wie `m_pTabWnd` werden in der [MDITabsDemo-Beispiel: MFC-im Registerkartenformat MDI-Anwendung](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

##  <a name="m_strtext"></a>  CMFCTabToolTipInfo::m_strText

Der QuickInfo-Text.

```
CString m_strText;
```

### <a name="remarks"></a>Hinweise

Wenn die Zeichenfolge leer ist, wird die QuickInfo nicht angezeigt.

### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt wie `m_strText` werden in der [MDITabsDemo-Beispiel: MFC-im Registerkartenformat MDI-Anwendung](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)
