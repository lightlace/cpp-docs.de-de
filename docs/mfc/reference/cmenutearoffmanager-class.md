---
title: Klasse CMenuTearOffManager | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMenuTearOffManager
dev_langs:
- C++
helpviewer_keywords:
- CMenuTearOffManager class
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
caps.latest.revision: 31
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 53677bbea54e428e5f080f5c1f73c576abcf99a5
ms.lasthandoff: 02/24/2017

---
# <a name="cmenutearoffmanager-class"></a>CMenuTearOffManager-Klasse
Verwaltet abtrennbare Menüs. Ein abtrennbares Menü ist ein Menü in der Menüleiste. Der Benutzer kann ein solches Menü von der Menüleiste abtrennen, wodurch das Menü beliebig positionierbar wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMenuTearOffManager : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
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
 Abtrennbare Menüs in Ihrer Anwendung verwenden zu können, benötigen Sie ein `CMenuTearOffManager` Objekt. In den meisten Fällen nicht erstellen oder Initialisieren einer `CMenuTearOffManager` direkt. Dies erfolgt für die Sie beim Aufrufen der [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) Funktion.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie zum Erstellen und Initialisieren einer `CMenuTearOffManager` -Objekt durch Aufrufen der `CWinAppEX::EnableTearOffMenus` Methode. Dieser Codeausschnitt ist Teil der [WordPad-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad&#12;](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CMenuTearOffManager`   
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmenutearoffmanager.h  
  
##  <a name="a-namebuilda--cmenutearoffmanagerbuild"></a><a name="build"></a>CMenuTearOffManager::Build  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void Build(
    UINT uiTearOffBarID,  
    CString& strText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiTearOffBarID`  
 [in] `strText`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namecmenutearoffmanagera--cmenutearoffmanagercmenutearoffmanager"></a><a name="cmenutearoffmanager"></a>CMenuTearOffManager::CMenuTearOffManager  
 Erstellt eine [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) Objekt.  
  
```  
CMenuTearOffManager();
```  
  
### <a name="remarks"></a>Hinweise  
 In den meisten Fällen erstellen Sie keine `CMenuTearOffManager` manuell. Das Framework der Anwendung erstellt die `CMenuTearOffManager` -Objekt beim Aufruf von [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus).  
  
##  <a name="a-namegetregpatha--cmenutearoffmanagergetregpath"></a><a name="getregpath"></a>CMenuTearOffManager::GetRegPath  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
LPCTSTR GetRegPath() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameinitializea--cmenutearoffmanagerinitialize"></a><a name="initialize"></a>CMenuTearOffManager::Initialize  
 Initialisiert eine [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) Objekt.  
  
```  
BOOL Initialize(
    LPCTSTR lpszRegEntry,  
    UINT uiTearOffMenuFirst,  
    UINT uiTearOffMenuLast);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszRegEntry`  
 Eine Zeichenfolge, die den Pfad eines Registrierungseintrags enthält. Die Anwendung speichert die Einstellungen für abtrennbare Balken in diesem Registrierungseintrag.  
  
 [in] `uiTearOffMenuFirst`  
 Das erste Menü-ID für eine Tearoff-Menü.  
  
 [in] `uiTearOffMenuLast`  
 Die letzte ID für eine Tearoff-Menü.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Den Bereich der Menü-IDs aus `uiTearOffMenuFirst` an `uiTearOffMenuLast` muss eine fortlaufende Intervall. Das Zeitintervall definiert die Anzahl der abtrennbare Menüs, die gleichzeitig in der Anwendung angezeigt werden können.  
  
##  <a name="a-nameisdynamicida--cmenutearoffmanagerisdynamicid"></a><a name="isdynamicid"></a>CMenuTearOffManager::IsDynamicID  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsDynamicID(UINT uiID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiID`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameparsea--cmenutearoffmanagerparse"></a><a name="parse"></a>CMenuTearOffManager::Parse  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
UINT Parse(CString& str);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `str`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namereseta--cmenutearoffmanagerreset"></a><a name="reset"></a>CMenuTearOffManager::Reset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void Reset(HMENU hmenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hmenu`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetinusea--cmenutearoffmanagersetinuse"></a><a name="setinuse"></a>CMenuTearOffManager::SetInUse  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetInUse(
    UINT uiCmdId,  
    BOOL bUse = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdId`  
 [in] `bUse`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetuptearoffmenusa--cmenutearoffmanagersetuptearoffmenus"></a><a name="setuptearoffmenus"></a>CMenuTearOffManager::SetupTearOffMenus  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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

