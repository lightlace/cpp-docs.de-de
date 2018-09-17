---
title: CMenuTearOffManager-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0ca3af6aba4c208672038de2ca663efdb2cc9d9a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700933"
---
# <a name="cmenutearoffmanager-class"></a>CMenuTearOffManager-Klasse
Verwaltet abtrennbare Menüs. Ein abtrennbares Menü ist ein Menü in der Menüleiste. Der Benutzer kann ein solches Menü von der Menüleiste abtrennen, wodurch das Menü beliebig positionierbar wird.  
  
   Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.  
   
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
|[CMenuTearOffManager::Initialize](#initialize)|Initialisiert eine `CMenuTearOffManager` Objekt.|  
|[CMenuTearOffManager::IsDynamicID](#isdynamicid)||  
|[CMenuTearOffManager::Parse](#parse)||  
|[CMenuTearOffManager::Reset](#reset)||  
|[CMenuTearOffManager::SetInUse](#setinuse)||  
|[CMenuTearOffManager::SetupTearOffMenus](#setuptearoffmenus)||  
  
## <a name="remarks"></a>Hinweise  
 Um abtrennbare Menüs in Ihrer Anwendung verwenden zu können, benötigen Sie eine `CMenuTearOffManager` Objekt. In den meisten Fällen nicht erstellen oder Initialisieren einer `CMenuTearOffManager` direkt. Dies wird für Sie erledigt, beim Aufrufen der [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) Funktion.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie zum Erstellen und initialisieren eine `CMenuTearOffManager` -Objekt durch Aufrufen der `CWinAppEX::EnableTearOffMenus` Methode. Dieser Codeausschnitt ist Teil des [WordPad-Beispiels](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#12](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMenuTearOffManager`   
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmenutearoffmanager.h  
  
##  <a name="build"></a>  CMenuTearOffManager::Build  

  
```  
void Build(
    UINT uiTearOffBarID,  
    CString& strText);
```  
  
### <a name="parameters"></a>Parameter  
*uiTearOffBarID*<br/>
[in] [in] *StrText*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="cmenutearoffmanager"></a>  CMenuTearOffManager::CMenuTearOffManager  
 Erstellt eine [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) Objekt.  
  
```  
CMenuTearOffManager();
```  
  
### <a name="remarks"></a>Hinweise  
 In den meisten Fällen sollten Sie keine erstellen eine `CMenuTearOffManager` manuell. Das Framework der Anwendung erstellt die `CMenuTearOffManager` Objekt beim Aufrufen [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus).  
  
##  <a name="getregpath"></a>  CMenuTearOffManager::GetRegPath  

  
```  
LPCTSTR GetRegPath() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="initialize"></a>  CMenuTearOffManager::Initialize  
 Initialisiert eine [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) Objekt.  
  
```  
BOOL Initialize(
    LPCTSTR lpszRegEntry,  
    UINT uiTearOffMenuFirst,  
    UINT uiTearOffMenuLast);
```  
  
### <a name="parameters"></a>Parameter  
*lpszRegEntry*<br/>
[in] Eine Zeichenfolge, die den Pfad eines Registrierungseintrags enthält. Ihre Anwendungen speichert die Einstellungen für abtrennbare Balken in diesen Registrierungseintrag an.  
  
*uiTearOffMenuFirst*<br/>
[in] Das erste Menü-ID für ein abtrennbares Menü.  
  
*uiTearOffMenuLast*<br/>
[in] Die letzte Menü-ID für ein abtrennbares Menü.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Den Bereich der Menü-ID von *UiTearOffMenuFirst* zu *UiTearOffMenuLast* muss eine fortlaufende Intervall sein. Das Intervall definiert die Anzahl der abtrennbare Menüs, die zur gleichen Zeit in der Anwendung angezeigt werden können.  
  
##  <a name="isdynamicid"></a>  CMenuTearOffManager::IsDynamicID  

  
```  
BOOL IsDynamicID(UINT uiID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *UiID*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="parse"></a>  CMenuTearOffManager::Parse  

  
```  
UINT Parse(CString& str);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *str*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="reset"></a>  CMenuTearOffManager::Reset  

  
```  
void Reset(HMENU hmenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Hmenu*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setinuse"></a>  CMenuTearOffManager::SetInUse  

  
```  
void SetInUse(
    UINT uiCmdId,  
    BOOL bUse = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*uiCmdId*<br/>
[in] [in] *bVerwenden*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setuptearoffmenus"></a>  CMenuTearOffManager::SetupTearOffMenus  

  
```  
void SetupTearOffMenus(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *hMenu*  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)
