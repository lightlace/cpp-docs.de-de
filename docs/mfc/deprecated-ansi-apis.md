---
title: Veraltete ANSI-APIs | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, ANSI deprecated methods
ms.assetid: c7c5a6fd-95e4-4bee-b3d5-d3826c30947d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d612cca5d0c95b411f5278fe92404166d26b53b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342058"
---
# <a name="deprecated-ansi-apis"></a>Veraltete ANSI-APIs
Die Microsoft Foundation Class (MFC)-Bibliothek ist in Bezug auf Klassen und Methoden, die auf den Unicode-Zeichensatz basieren migrieren. Folglich sind die ANSI-Versionen von mehreren MFC-Methoden veraltet. Verwenden Sie die Unicode-Versionen dieser Methoden in Zukunft Anwendungen.  
  
 Ab Windows-Standardsteuerelemente Version 6.1, gelieferten [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)], die folgenden ANSI-Methoden sind veraltet.  
  
## <a name="cbutton-class"></a>CButton-Klasse  
  
```  
AFX_ANSI_DEPRECATED BOOL GetIdealSize(LPSIZE psize) const;

 
AFX_ANSI_DEPRECATED BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist) const;

 
AFX_ANSI_DEPRECATED BOOL GetTextMargin(LPRECT pmargin) const;

 
AFX_ANSI_DEPRECATED BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);

AFX_ANSI_DEPRECATED BOOL SetTextMargin(LPRECT pmargin);
```  
  
## <a name="ccomboboxex-class"></a>CComboBoxEx-Klasse  
  
```  
AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
## <a name="cedit-class"></a>CEdit-Klasse  
  
```  
AFX_ANSI_DEPRECATED BOOL GetCueBanner(LPWSTR lpszText,
    int cchText) const;

 
AFX_ANSI_DEPRECATED BOOL SetCueBanner(LPCWSTR lpszText,
    BOOL fDrawIfFocused = FALSE);
```  
  
## <a name="clinkctrl-class"></a>CLinkCtrl-Klasse  
 Die gesamte Klasse ist veraltet.  
  
## <a name="clistctrl-class"></a>CListCtrl-Klasse  
  
```  
AFX_ANSI_DEPRECATED void CancelEditLabel();

AFX_ANSI_DEPRECATED int EnableGroupView(BOOL fEnable);

AFX_ANSI_DEPRECATED int GetGroupInfo(int iGroupId,
    PLVGROUP pgrp) const;

 
AFX_ANSI_DEPRECATED void GetGroupMetrics(PLVGROUPMETRICS pGroupMetrics) const;

 
AFX_ANSI_DEPRECATED BOOL GetInsertMark(LPLVINSERTMARK lvim) const;

 
AFX_ANSI_DEPRECATED COLORREF GetInsertMarkColor() const;

 
AFX_ANSI_DEPRECATED int GetInsertMarkRect(LPRECT pRect) const;

 
AFX_ANSI_DEPRECATED COLORREF GetOutlineColor() const;

 
AFX_ANSI_DEPRECATED UINT GetSelectedColumn() const;

 
AFX_ANSI_DEPRECATED BOOL GetTileInfo(PLVTILEINFO pti) const;

 
AFX_ANSI_DEPRECATED BOOL GetTileViewInfo(PLVTILEVIEWINFO ptvi) const;

 
AFX_ANSI_DEPRECATED DWORD GetView() const;

 
AFX_ANSI_DEPRECATED BOOL HasGroup(int iGroupId) const;

 
AFX_ANSI_DEPRECATED int InsertGroup(int index,
    PLVGROUP pgrp);

AFX_ANSI_DEPRECATED void InsertGroupSorted(PLVINSERTGROUPSORTED pStructInsert);

AFX_ANSI_DEPRECATED int InsertMarkHitTest(LPPOINT pPoint,
    LPLVINSERTMARK lvim) const;

 
AFX_ANSI_DEPRECATED BOOL IsGroupViewEnabled() const;

 
AFX_ANSI_DEPRECATED void MoveGroup(int iGroupId,
    int toIndex);

AFX_ANSI_DEPRECATED void MoveItemToGroup(int idItemFrom,
    int idGroupTo);

AFX_ANSI_DEPRECATED void RemoveAllGroups();

AFX_ANSI_DEPRECATED int RemoveGroup(int iGroupId);

AFX_ANSI_DEPRECATED BOOL SetGroupInfo(int iGroupId,
    PLVGROUP pGroup);

AFX_ANSI_DEPRECATED void SetGroupMetrics(PLVGROUPMETRICS pGroupMetrics);

AFX_ANSI_DEPRECATED BOOL SetInfoTip(PLVSETINFOTIP plvInfoTip);

AFX_ANSI_DEPRECATED BOOL SetInsertMark(LPLVINSERTMARK lvim);

AFX_ANSI_DEPRECATED COLORREF SetInsertMarkColor(COLORREF color);

AFX_ANSI_DEPRECATED COLORREF SetOutlineColor(COLORREF color);

AFX_ANSI_DEPRECATED void SetSelectedColumn(int iCol);

AFX_ANSI_DEPRECATED BOOL SetTileInfo(PLVTILEINFO pti);

AFX_ANSI_DEPRECATED BOOL SetTileViewInfo(PLVTILEVIEWINFO ptvi);

AFX_ANSI_DEPRECATED DWORD SetView(int iView);

AFX_ANSI_DEPRECATED BOOL SortGroups(PFNLVGROUPCOMPARE _pfnGroupCompare,
    LPVOID _plv);
```  
  
## <a name="crebarctrl-class"></a>CReBarCtrl-Klasse  
  
```  
AFX_ANSI_DEPRECATED void GetBandMargins(PMARGINS pMargins) const;

 
AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
## <a name="ctoolbarctrl-class"></a>CToolBarCtrl-Klasse  
  
```  
AFX_ANSI_DEPRECATED void GetMetrics(LPTBMETRICS ptbm) const;

 
AFX_ANSI_DEPRECATED void SetMetrics(LPTBMETRICS ptbm);

AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
## <a name="ctooltipctrl-class"></a>CToolTipCtrl-Klasse  
  
```  
AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
## <a name="see-also"></a>Siehe auch  
 [Anforderungen für die Erstellung von Windows Vista-Standardsteuerelementen](../mfc/build-requirements-for-windows-vista-common-controls.md)

