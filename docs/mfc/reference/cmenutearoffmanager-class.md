---
title: CMenuTearOffManager Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Build
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::GetRegPath
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Initialize
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::IsDynamicID
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Parse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Reset
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetInUse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetupTearOffMenus
dev_langs: C++
helpviewer_keywords:
- CMenuTearOffManager [MFC], CMenuTearOffManager
- CMenuTearOffManager [MFC], Build
- CMenuTearOffManager [MFC], GetRegPath
- CMenuTearOffManager [MFC], Initialize
- CMenuTearOffManager [MFC], IsDynamicID
- CMenuTearOffManager [MFC], Parse
- CMenuTearOffManager [MFC], Reset
- CMenuTearOffManager [MFC], SetInUse
- CMenuTearOffManager [MFC], SetupTearOffMenus
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
caps.latest.revision: "31"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: efb1b7acc2f4eb779de49559b5b566e89d518a0e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmenutearoffmanager-class"></a>CMenuTearOffManager-Klasse
Verwaltet abtrennbare Menüs. Ein abtrennbares Menü ist ein Menü in der Menüleiste. Der Benutzer kann ein solches Menü von der Menüleiste abtrennen, wodurch das Menü beliebig positionierbar wird.  
  
   [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
   
## <a name="syntax"></a>Syntax  
  
```  
class CMenuTearOffManager : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMenuTearOffManager::CMenuTearOffManager](#cmenutearoffmanager)|Erstellt ein `CMenuTearOffManager`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMenuTearOffManager::Build](#build)||  
|[CMenuTearOffManager::GetRegPath](#getregpath)||  
|[CMenuTearOffManager::Initialize](#initialize)|Initialisiert ein `CMenuTearOffManager` Objekt.|  
|[CMenuTearOffManager::IsDynamicID](#isdynamicid)||  
|[CMenuTearOffManager::Parse](#parse)||  
|[CMenuTearOffManager::Reset](#reset)||  
|[CMenuTearOffManager::SetInUse](#setinuse)||  
|[CMenuTearOffManager::SetupTearOffMenus](#setuptearoffmenus)||  
  
## <a name="remarks"></a>Hinweise  
 Um abtrennbare Menüs in Ihrer Anwendung verwenden zu können, benötigen Sie ein `CMenuTearOffManager` Objekt. In den meisten Fällen wird nicht erstellen oder Initialisieren einer `CMenuTearOffManager` -Objekts direkt. Dies erfolgt Sie beim Aufrufen der [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) Funktion.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie zum Erstellen und Initialisieren einer `CMenuTearOffManager` Objekt durch Aufrufen der `CWinAppEX::EnableTearOffMenus` Methode. Dieser Codeausschnitt ist Teil des [WordPad-Beispiels](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#12](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMenuTearOffManager`   
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmenutearoffmanager.h  
  
##  <a name="build"></a>CMenuTearOffManager::Build  

  
```  
void Build(
    UINT uiTearOffBarID,  
    CString& strText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiTearOffBarID`  
 [in] `strText`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="cmenutearoffmanager"></a>CMenuTearOffManager::CMenuTearOffManager  
 Erstellt eine [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) Objekt.  
  
```  
CMenuTearOffManager();
```  
  
### <a name="remarks"></a>Hinweise  
 In den meisten Fällen sollten Sie keine erstellen eine `CMenuTearOffManager` manuell. Das Framework der Anwendung erstellt die `CMenuTearOffManager` Objekt beim Aufrufen von [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus).  
  
##  <a name="getregpath"></a>CMenuTearOffManager::GetRegPath  

  
```  
LPCTSTR GetRegPath() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="initialize"></a>CMenuTearOffManager::Initialize  
 Initialisiert eine [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) Objekt.  
  
```  
BOOL Initialize(
    LPCTSTR lpszRegEntry,  
    UINT uiTearOffMenuFirst,  
    UINT uiTearOffMenuLast);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszRegEntry`  
 Eine Zeichenfolge, die den Pfad eines Registrierungseintrags enthält. Ihre Anwendungen speichert die Einstellungen für abtrennbare Balken in diesen Registrierungseintrag an.  
  
 [in] `uiTearOffMenuFirst`  
 Das erste Menü-ID für ein abtrennbares Menü.  
  
 [in] `uiTearOffMenuLast`  
 Die letzte Menü-ID für ein abtrennbares Menü.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Der Bereich der Menü-IDs aus `uiTearOffMenuFirst` auf `uiTearOffMenuLast` muss eine fortlaufende Intervall. Das Intervall definiert die Anzahl der abtrennbare Menüs, die gleichzeitig in der Anwendung angezeigt werden können.  
  
##  <a name="isdynamicid"></a>CMenuTearOffManager::IsDynamicID  

  
```  
BOOL IsDynamicID(UINT uiID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiID`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="parse"></a>CMenuTearOffManager::Parse  

  
```  
UINT Parse(CString& str);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `str`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="reset"></a>CMenuTearOffManager::Reset  

  
```  
void Reset(HMENU hmenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hmenu`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setinuse"></a>CMenuTearOffManager::SetInUse  

  
```  
void SetInUse(
    UINT uiCmdId,  
    BOOL bUse = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdId`  
 [in] `bUse`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setuptearoffmenus"></a>CMenuTearOffManager::SetupTearOffMenus  

  
```  
void SetupTearOffMenus(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hMenu`  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)
