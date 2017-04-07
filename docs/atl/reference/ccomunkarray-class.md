---
title: Klasse CComUnkArray | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
caps.latest.revision: 17
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 94f1062ff3808f527874a8890eca95c9b655b1bf
ms.lasthandoff: 02/24/2017

---
# <a name="ccomunkarray-class"></a>CComUnkArray-Klasse
Diese Klasse speichert **IUnknown** Zeiger als Parameter verwendet wird, dient die [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Vorlagenklasse.  
  
## <a name="syntax"></a>Syntax  
  
```
template<unsigned int nMaxSize>
class CComUnkArray
```  
  
#### <a name="parameters"></a>Parameter  
 *nMaxSize*  
 Die maximale Anzahl von **IUnknown** Zeiger, die im statischen Array gespeichert werden können.  
  
## <a name="members"></a>Mitglieder  
  
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
|[CComUnkArray::GetCookie](#getcookie)|Rufen Sie diese Methode, um die zugeordnete Cookie Abrufen einer bestimmten **IUnknown** Zeiger.|  
|[CComUnkArray::GetUnknown](#getunknown)|Rufen Sie diese Methode zum Abrufen der **IUnknown** Zeiger, die mit einem bestimmten Cookie verknüpft ist.|  
|[CComUnkArray::Remove](#remove)|Rufen Sie diese Methode zum Entfernen einer **IUnknown** Zeiger aus dem Array.|  
  
## <a name="remarks"></a>Hinweise  
 **CComUnkArray** enthält eine feste Anzahl von **IUnknown** Zeigern, jede zeigen Sie eine Schnittstelle für eine Verbindung. **CComUnkArray** können verwendet werden, als Parameter an die [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Vorlagenklasse. **CComUnkArray\<1 >** ist eine Spezialisierung einer Klassenvorlage von **CComUnkArray** , die für einen Verbindungspunkt optimiert wurde.  
  
 Die **CComUnkArray** Methoden [beginnen](#begin) und [End](#end) kann zum Durchlaufen aller Verbindungspunkte (z. B., wenn ein Ereignis ausgelöst wird) verwendet werden.  
  
 Finden Sie unter [Hinzufügen von Verbindungspunkten zu einem Objekt](../../atl/adding-connection-points-to-an-object.md) zeigen Sie ausführliche Informationen zum Automatisieren der Erstellung der Verbindung Proxys.  
  
> [!NOTE]
> **Hinweis** der Klasse [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) werden die **Klasse hinzufügen** Assistenten beim Erstellen eines Steuerelements die Verbindungspunkte verfügt. Wenn Sie die Anzahl der Verbindungspunkte manuell angeben möchten, ändern Sie den Verweis aus **CComDynamicUnkArray** auf `CComUnkArray<` *n* `>`, wobei *n* ist die Anzahl der Verbindungspunkte erforderlich.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="add"></a>CComUnkArray::Add  
 Rufen Sie diese Methode zum Hinzufügen einer **IUnknown** Zeiger auf das Array.  
  
```
DWORD Add(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnk*  
 Rufen Sie diese Methode zum Hinzufügen einer **IUnknown** Zeiger auf das Array.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Cookie, das den neu hinzugefügten Zeiger oder 0 zugeordnet, wenn das Array nicht groß genug, um den neuen Zeiger enthalten ist.  
  
##  <a name="begin"></a>CComUnkArray::begin  
 Gibt einen Zeiger auf den Anfang der Auflistung der **IUnknown** Schnittstellenzeiger.  
  
```
IUnknown**
    begin();
```     
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine **IUnknown** -Schnittstellenzeiger.  
  
### <a name="remarks"></a>Hinweise  
 Die Auflistung enthält Verweise auf Schnittstellen, die lokal gespeichert, als **IUnknown**. Wandeln Sie jede **IUnknown** Schnittstelle für den Typ der echten, und rufen Sie dann über ihn. Sie müssen nicht zuerst die Schnittstelle Abfragen.  
  
 Vor der Verwendung der **IUnknown** -Schnittstelle, sollten Sie überprüfen, dass es nicht **NULL**.  
  
##  <a name="ccomunkarray"></a>CComUnkArray::CComUnkArray  
 Der Konstruktor.  
  
```
CComUnkArray();
```  
  
### <a name="remarks"></a>Hinweise  
 Legt die Auflistung zum Speichern `nMaxSize` **IUnknown** -Zeigern und initialisiert die Zeiger auf **NULL**.  
  
##  <a name="end"></a>CComUnkArray::end  
 Gibt einen Zeiger auf eine Position hinter dem letzten **IUnknown** Zeiger in der Auflistung.  
  
```
IUnknown**
    end();
```     
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine **IUnknown** -Schnittstellenzeiger.  
  
### <a name="remarks"></a>Hinweise  
 Die `CComUnkArray` Methoden **beginnen** und **End** kann zum Durchlaufen aller Verbindungspunkte, z. B., wenn ein Ereignis ausgelöst wird.  
  
 [!code-cpp[NVC_ATL_COM&#44;](../../atl/codesnippet/cpp/ccomunkarray-class_1.cpp)]  
  
##  <a name="getcookie"></a>CComUnkArray::GetCookie  
 Rufen Sie diese Methode, um die zugeordnete Cookie Abrufen einer bestimmten **IUnknown** Zeiger.  
  
```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```  
  
### <a name="parameters"></a>Parameter  
 `ppFind`  
 Die **IUnknown** Zeiger für das des zugehörigen Cookies erforderlich ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Cookie für die **IUnknown** Zeiger oder 0, wenn kein übereinstimmender **IUnknown** Zeiger gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn mehr als eine des gleichen Instanz **IUnknown** -Zeiger ist, gibt diese Funktion das Cookie für das erste Element zurück.  
  
##  <a name="getunknown"></a>CComUnkArray::GetUnknown  
 Rufen Sie diese Methode zum Abrufen der **IUnknown** Zeiger, die mit einem bestimmten Cookie verknüpft ist.  
  
```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Parameter  
 `dwCookie`  
 Das Cookie für die zugeordneten **IUnknown** Zeiger erforderlich ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die **IUnknown** Zeiger oder NULL, wenn keine übereinstimmende Cookie gefunden wird.  
  
##  <a name="remove"></a>CComUnkArray::Remove  
 Rufen Sie diese Methode zum Entfernen einer **IUnknown** Zeiger aus dem Array.  
  
```
BOOL Remove(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Parameter  
 `dwCookie`  
 Das Cookie verweisen auf die **IUnknown** Zeiger aus dem Array entfernt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** wird der Zeiger entfernt, **FALSE** andernfalls.  
  
## <a name="see-also"></a>Siehe auch  
 [CComDynamicUnkArray-Klasse](../../atl/reference/ccomdynamicunkarray-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

