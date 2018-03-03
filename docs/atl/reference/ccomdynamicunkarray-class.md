---
title: CComDynamicUnkArray Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::Add
- ATLCOM/ATL::CComDynamicUnkArray::begin
- ATLCOM/ATL::CComDynamicUnkArray::clear
- ATLCOM/ATL::CComDynamicUnkArray::end
- ATLCOM/ATL::CComDynamicUnkArray::GetAt
- ATLCOM/ATL::CComDynamicUnkArray::GetCookie
- ATLCOM/ATL::CComDynamicUnkArray::GetSize
- ATLCOM/ATL::CComDynamicUnkArray::GetUnknown
- ATLCOM/ATL::CComDynamicUnkArray::Remove
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5863c224ed47c70ce485bde3cd693c29afbfbc04
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccomdynamicunkarray-class"></a>CComDynamicUnkArray-Klasse
Diese Klasse speichert ein Array von **IUnknown** Zeiger.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComDynamicUnkArray
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComDynamicUnkArray::CComDynamicUnkArray](#ccomdynamicunkarray)|Konstruktor. Die Auflistungswerte initialisiert **NULL** und die Größe der Auflistung auf 0 (null).|  
|[CComDynamicUnkArray:: ~ CComDynamicUnkArray](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComDynamicUnkArray::Add](#add)|Rufen Sie diese Methode zum Hinzufügen einer `IUnknown` Zeiger auf das Array.|  
|[CComDynamicUnkArray::begin](#begin)|Gibt einen Zeiger auf das erste `IUnknown` Zeiger in der Auflistung.|  
|[CComDynamicUnkArray::clear](#clear)|Leert das Array an.|  
|[CComDynamicUnkArray::end](#end)|Gibt einen Zeiger auf eine Position hinter dem letzten **IUnknown** Zeiger in der Auflistung.|  
|[CComDynamicUnkArray::GetAt](#getat)|Ruft das Element am angegebenen Index ab.|  
|[CComDynamicUnkArray::GetCookie](#getcookie)|Rufen Sie diese Methode zum Abrufen der zugeordneten Cookies einer bestimmten **IUnknown** Zeiger.|  
|[CComDynamicUnkArray::GetSize](#getsize)|Gibt die Länge eines Arrays zurück.|  
|[CComDynamicUnkArray::GetUnknown](#getunknown)|Rufen Sie diese Methode zum Abrufen der **IUnknown** Zeiger mit einem bestimmten Cookie verknüpft sind.|  
|[CComDynamicUnkArray::Remove](#remove)|Rufen Sie diese Methode zum Entfernen einer **IUnknown** Zeiger aus dem Array.|  
  
## <a name="remarks"></a>Hinweise  
 **CComDynamicUnkArray** enthält ein dynamisch zugeordnetes Arrays von **IUnknown** Zeigern, zeigen Sie jeweils eine Schnittstelle für eine Verbindung. **CComDynamicUnkArray** können verwendet werden, als Parameter an die [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Vorlagenklasse.  
  
 Die **CComDynamicUnkArray** Methoden [beginnen](#begin) und [End](#end) können verwendet werden, um die Schleife durchlaufen alle Verbindungspunkte (z. B., wenn ein Ereignis ausgelöst wird).  
  
 Finden Sie unter [Hinzufügen von Verbindungspunkten zu einem Objekt](../../atl/adding-connection-points-to-an-object.md) zeigen Sie ausführliche Informationen zum Automatisieren der Erstellung der Verbindung Proxys.  
  
> [!NOTE]
> **Hinweis** Klasse **CComDynamicUnkArray** dient der **Klasse hinzufügen** Assistenten beim Erstellen eines Steuerelements Verbindungspunkte besitzt. Wenn Sie die Anzahl von Verbindungspunkten manuell angeben möchten, ändern Sie den Verweis aus **CComDynamicUnkArray** auf `CComUnkArray<`  *n*  `>`, wobei  *n*  ist die Anzahl der Verbindungspunkte erforderlich.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="add"></a>CComDynamicUnkArray::Add  
 Rufen Sie diese Methode zum Hinzufügen einer **IUnknown** Zeiger auf das Array.  
  
```
DWORD Add(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnk*  
 Die **IUnknown** Zeiger auf das Array hinzufügen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Cookie, das den neu hinzugefügten Zeiger zugeordnet.  
  
##  <a name="begin"></a>CComDynamicUnkArray::begin  
 Gibt einen Zeiger auf den Anfang der Auflistung der **IUnknown** Schnittstellenzeigern.  
  
```
IUnknown**
    begin();
```     
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein **IUnknown** Schnittstellenzeiger auf.  
  
### <a name="remarks"></a>Hinweise  
 Die Auflistung enthält Zeiger auf die Schnittstellen, die lokal gespeichert werden, als **IUnknown**. Jede Umwandlung **IUnknown** Schnittstelle zu den tatsächlichen Schnittstellentyp, und rufen Sie anschließend über ihn. Sie müssen nicht zuerst für die Schnittstelle abzufragen.  
  
 Vor der Verwendung der **IUnknown** -Schnittstelle, sollten Sie überprüfen, dass es nicht **NULL**.  
  
##  <a name="clear"></a>CComDynamicUnkArray::clear  
 Leert das Array an.  
  
```
void clear();
```  
  
##  <a name="ccomdynamicunkarray"></a>CComDynamicUnkArray::CComDynamicUnkArray  
 Der Konstruktor.  
  
```
CComDynamicUnkArray();
```  
  
### <a name="remarks"></a>Hinweise  
 Legt die Größe der Auflistung auf 0 (null) fest und initialisiert die Werte, die **NULL**. Der Destruktor gibt die Auflistung bei Bedarf frei.  
  
##  <a name="dtor"></a>CComDynamicUnkArray:: ~ CComDynamicUnkArray  
 Der Destruktor.  
  
```
~CComDynamicUnkArray();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt die vom Konstruktor Klasse reservierten Ressourcen frei.  
  
##  <a name="end"></a>CComDynamicUnkArray::end  
 Gibt einen Zeiger auf eine Position hinter dem letzten **IUnknown** Zeiger in der Auflistung.  
  
```
IUnknown**
    end();
```     
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein **IUnknown** Schnittstellenzeiger auf.  
  
##  <a name="getat"></a>CComDynamicUnkArray::GetAt  
 Ruft das Element am angegebenen Index ab.  
  
```
IUnknown* GetAt(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des abzurufenden Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) Schnittstelle.  
  
##  <a name="getcookie"></a>CComDynamicUnkArray::GetCookie  
 Rufen Sie diese Methode zum Abrufen der zugeordneten Cookies einer bestimmten **IUnknown** Zeiger.  
  
```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```  
  
### <a name="parameters"></a>Parameter  
 `ppFind`  
 Die **IUnknown** Zeiger für das des zugehörigen Cookies erforderlich ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Cookie zugeordnet der **IUnknown** Zeiger ist, oder 0 (null), wenn kein übereinstimmender **IUnknown** Zeiger befindet.  
  
### <a name="remarks"></a>Hinweise  
 Wenn mehr als eine des gleichen Instanz **IUnknown** -Zeiger ist, gibt diese Funktion das Cookie auf das erste Verzeichnis zurück.  
  
##  <a name="getsize"></a>CComDynamicUnkArray::GetSize  
 Gibt die Länge eines Arrays zurück.  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge des Arrays.  
  
##  <a name="getunknown"></a>CComDynamicUnkArray::GetUnknown  
 Rufen Sie diese Methode zum Abrufen der **IUnknown** Zeiger mit einem bestimmten Cookie verknüpft sind.  
  
```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Parameter  
 `dwCookie`  
 Das Cookie für die zugeordneten **IUnknown** Zeiger erforderlich ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die **IUnknown** Zeiger oder NULL, wenn keine übereinstimmenden Cookie gefunden wird.  
  
##  <a name="remove"></a>CComDynamicUnkArray::Remove  
 Rufen Sie diese Methode zum Entfernen einer **IUnknown** Zeiger aus dem Array.  
  
```
BOOL Remove(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Parameter  
 `dwCookie`  
 Das Cookie verweisen auf die **IUnknown** Zeiger aus dem Array entfernt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, wenn der Zeiger entfernt wird. andernfalls "false".  
  
## <a name="see-also"></a>Siehe auch  
 [CComUnkArray-Klasse](../../atl/reference/ccomunkarray-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
