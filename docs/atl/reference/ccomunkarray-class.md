---
title: CComUnkArray Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComUnkArray
- ATLCOM/ATL::CComUnkArray
- ATLCOM/ATL::CComUnkArray::CComUnkArray
- ATLCOM/ATL::CComUnkArray::Add
- ATLCOM/ATL::CComUnkArray::begin
- ATLCOM/ATL::CComUnkArray::end
- ATLCOM/ATL::CComUnkArray::GetCookie
- ATLCOM/ATL::CComUnkArray::GetUnknown
- ATLCOM/ATL::CComUnkArray::Remove
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- CComUnkArray class
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3ca462648a43869b11984e4582c8eb2c3dfaece7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccomunkarray-class"></a>CComUnkArray-Klasse
Diese Klasse speichert **IUnknown** Zeiger, und dient zum als Parameter an die [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Vorlagenklasse.  
  
## <a name="syntax"></a>Syntax  
  
```
template<unsigned int nMaxSize>
class CComUnkArray
```  
  
#### <a name="parameters"></a>Parameter  
 *nMaxSize*  
 Die maximale Anzahl von **IUnknown** Zeiger, die den statischen Array aufnehmen können.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComUnkArray::CComUnkArray](#ccomunkarray)|Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComUnkArray::Add](#add)|Rufen Sie diese Methode zum Hinzufügen einer **IUnknown** Zeiger auf das Array.|  
|[CComUnkArray::begin](#begin)|Gibt einen Zeiger auf das erste **IUnknown** Zeiger in der Auflistung.|  
|[CComUnkArray::end](#end)|Gibt einen Zeiger auf eine Position hinter dem letzten **IUnknown** Zeiger in der Auflistung.|  
|[CComUnkArray::GetCookie](#getcookie)|Rufen Sie diese Methode zum Abrufen der zugeordneten Cookies einer bestimmten **IUnknown** Zeiger.|  
|[CComUnkArray::GetUnknown](#getunknown)|Rufen Sie diese Methode zum Abrufen der **IUnknown** Zeiger mit einem bestimmten Cookie verknüpft sind.|  
|[CComUnkArray::Remove](#remove)|Rufen Sie diese Methode zum Entfernen einer **IUnknown** Zeiger aus dem Array.|  
  
## <a name="remarks"></a>Hinweise  
 **CComUnkArray** enthält eine feste Anzahl von **IUnknown** Zeigern, zeigen Sie jeweils eine Schnittstelle für eine Verbindung. **CComUnkArray** können verwendet werden, als Parameter an die [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Vorlagenklasse. **CComUnkArray\<1 >** ist eine vorlagenspezialisierung der **CComUnkArray** , die für einen Verbindungspunkt optimiert wurde.  
  
 Die **CComUnkArray** Methoden [beginnen](#begin) und [End](#end) können verwendet werden, um die Schleife durchlaufen alle Verbindungspunkte (z. B., wenn ein Ereignis ausgelöst wird).  
  
 Finden Sie unter [Hinzufügen von Verbindungspunkten zu einem Objekt](../../atl/adding-connection-points-to-an-object.md) zeigen Sie ausführliche Informationen zum Automatisieren der Erstellung der Verbindung Proxys.  
  
> [!NOTE]
> **Hinweis** Klasse [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) dient der **Klasse hinzufügen** Assistenten beim Erstellen eines Steuerelements Verbindungspunkte besitzt. Wenn Sie die Anzahl von Verbindungspunkten manuell angeben möchten, ändern Sie den Verweis aus **CComDynamicUnkArray** auf `CComUnkArray<`  *n*  `>`, wobei  *n*  ist die Anzahl der Verbindungspunkte erforderlich.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="add"></a>CComUnkArray::Add  
 Rufen Sie diese Methode zum Hinzufügen einer **IUnknown** Zeiger auf das Array.  
  
```
DWORD Add(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnk*  
 Rufen Sie diese Methode zum Hinzufügen einer **IUnknown** Zeiger auf das Array.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Cookie, das den neu hinzugefügten Zeiger oder 0 zugeordnet, wenn das Array nicht groß genug ist, um den neuen Zeiger enthalten ist.  
  
##  <a name="begin"></a>CComUnkArray::begin  
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
  
##  <a name="ccomunkarray"></a>CComUnkArray::CComUnkArray  
 Der Konstruktor.  
  
```
CComUnkArray();
```  
  
### <a name="remarks"></a>Hinweise  
 Festlegen der Auflistung zum Speichern `nMaxSize` **IUnknown** Zeigern und initialisiert die Zeiger auf **NULL**.  
  
##  <a name="end"></a>CComUnkArray::end  
 Gibt einen Zeiger auf eine Position hinter dem letzten **IUnknown** Zeiger in der Auflistung.  
  
```
IUnknown**
    end();
```     
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein **IUnknown** Schnittstellenzeiger auf.  
  
### <a name="remarks"></a>Hinweise  
 Die `CComUnkArray` Methoden **beginnen** und **End** können verwendet werden, um alle Verbindungspunkte, z. B. durchlaufen, wenn ein Ereignis ausgelöst wird.  
  
 [!code-cpp[NVC_ATL_COM#44](../../atl/codesnippet/cpp/ccomunkarray-class_1.cpp)]  
  
##  <a name="getcookie"></a>CComUnkArray::GetCookie  
 Rufen Sie diese Methode zum Abrufen der zugeordneten Cookies einer bestimmten **IUnknown** Zeiger.  
  
```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```  
  
### <a name="parameters"></a>Parameter  
 `ppFind`  
 Die **IUnknown** Zeiger für das des zugehörigen Cookies erforderlich ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Cookie zugeordnet der **IUnknown** Zeiger bzw. 0, wenn kein übereinstimmender **IUnknown** Zeiger befindet.  
  
### <a name="remarks"></a>Hinweise  
 Wenn mehr als eine des gleichen Instanz **IUnknown** -Zeiger ist, gibt diese Funktion das Cookie auf das erste Verzeichnis zurück.  
  
##  <a name="getunknown"></a>CComUnkArray::GetUnknown  
 Rufen Sie diese Methode zum Abrufen der **IUnknown** Zeiger mit einem bestimmten Cookie verknüpft sind.  
  
```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Parameter  
 `dwCookie`  
 Das Cookie für die zugeordneten **IUnknown** Zeiger erforderlich ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die **IUnknown** Zeiger oder NULL, wenn keine übereinstimmenden Cookie gefunden wird.  
  
##  <a name="remove"></a>CComUnkArray::Remove  
 Rufen Sie diese Methode zum Entfernen einer **IUnknown** Zeiger aus dem Array.  
  
```
BOOL Remove(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Parameter  
 `dwCookie`  
 Das Cookie verweisen auf die **IUnknown** Zeiger aus dem Array entfernt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** entfernt der Zeiger, **"false"** andernfalls.  
  
## <a name="see-also"></a>Siehe auch  
 [CComDynamicUnkArray-Klasse](../../atl/reference/ccomdynamicunkarray-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
