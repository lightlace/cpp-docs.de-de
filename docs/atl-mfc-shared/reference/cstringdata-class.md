---
title: CStringData Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringData
dev_langs:
- C++
helpviewer_keywords:
- CStringData class
- shared classes, CStringData
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
caps.latest.revision: 16
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b7dfebebbec7acc774fa2e63ab9fafed788f679a
ms.lasthandoff: 02/24/2017

---
# <a name="cstringdata-class"></a>CStringData-Klasse
Diese Klasse stellt die Daten von einem String-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```
struct CStringData
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[AddRef](#addref)|Inkrementiert den Verweiszähler des String-Objekts.|  
|[data](#data)|Ruft die Daten eines Zeichenfolgenobjekts ab.|  
|[IsLocked](#islocked)|Bestimmt, ob der Puffer des zugeordneten Objekts gesperrt ist.|  
|[IsShared](#isshared)|Bestimmt, ob der Puffer des zugeordneten Objekts gegenwärtig freigegeben ist.|  
|[Sperren](#lock)|Sperrt den Puffer des zugeordneten Objekts.|  
|[Version](#release)|Gibt das angegebene String-Objekt frei.|  
|[Entsperren](#unlock)|Hebt die Sperre des Objekts zugeordneten Puffer.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[nAllocLength](#nalloclength)|Länge der zugeordneten Daten in `XCHAR`s (einschließlich abschließenden Nullzeichen)|  
|[nDataLength](#ndatalength)|Länge der aktuell verwendeten Daten in `XCHAR`s (einschließlich abschließenden Nullzeichen)|  
|[nRefs](#nrefs)|Der aktuelle Verweiszähler des Objekts.|  
|[pStringMgr](#pstringmgr)|Ein Zeiger auf die Zeichenfolgen-Manager von diesem String-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse sollte nur von Entwicklern zum Implementieren von benutzerdefinierten-Manager verwendet werden. Weitere Informationen zu benutzerdefinierten-Manager, finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)  
  
 Diese Klasse kapselt die verschiedenen Typen von Informationen und Daten, die eine höhere String-Objekt zugeordnet sind, z. B. [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), oder [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md) Objekte. Jede höhere String-Objekt enthält einen Zeiger auf die zugehörigen `CStringData` Objekt, können mehrere String-Objekte auf das gleiche Zeichenfolgenobjekt für Daten. Diese Beziehung wird durch den Verweiszähler dargestellt ( `nRefs`) von der `CStringData` Objekt.  
  
> [!NOTE]
>  In bestimmten Fällen eine String-Datentyp (z. B. **CFixedString**) ein Datenobjekt Zeichenfolge mit mehr als eine höhere String-Objekt wird nicht freigeben. Weitere Informationen hierzu finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
 Diese Daten besteht aus:  
  
-   Der Speicher-Manager (des Typs [IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)) der Zeichenfolge.  
  
-   Die aktuelle Länge ( [nDataLength](#ndatalength)) der Zeichenfolge.  
  
-   Die zugeordnete Länge ( [nAllocLength](#nalloclength)) der Zeichenfolge. Aus Gründen der Leistung kann dies von der Länge der Zeichenfolge für das aktuelle abweichen.  
  
-   Der aktuelle Verweiszähler ( [nRefs](#nrefs)) von der `CStringData` Objekt. Dieser Wert wird verwendet, bei der Bestimmung, wie viele Zeichenfolgenobjekte dieselbe Freigabe `CStringData` Objekt.  
  
-   Die tatsächliche Zeichenpuffer ( [Daten](#data)) der Zeichenfolge.  
  
    > [!NOTE]
    >  Die tatsächliche Zeichenpuffer String-Objekt wird von der Zeichenfolgen-Manager zugeordnet und angehängt der `CStringData` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsimpstr.h  
  
##  <a name="a-nameaddrefa--cstringdataaddref"></a><a name="addref"></a>CStringData::AddRef  
 Inkrementiert den Verweiszähler des String-Objekt.  
  
```
void AddRef() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Inkrementiert den Verweiszähler des String-Objekt.  
  
> [!NOTE]
>  Rufen Sie diese Methode nicht auf eine Zeichenfolge mit einer negativen Verweisanzahl, da eine negative Anzahl gibt an, dass der Zeichenfolgenpuffer gesperrt ist.  
  
##  <a name="a-namedataa--cstringdatadata"></a><a name="data"></a>CStringData::data  
 Gibt einen Zeiger auf den Zeichenpuffer eines Zeichenfolgenobjekts zurück.  
  
```
void* data() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Zeichenpuffer String-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um den aktuellen Zeichenpuffer zugeordnete String-Objekt zurückgeben.  
  
> [!NOTE]
>  Dieser Puffer ist nicht von zugeordnet der `CStringData` Objekt jedoch über den Zeichenfolgen-Manager bei Bedarf. Wenn zugeordnet, wird der Puffer auf das Datenobjekt Zeichenfolge angefügt.  
  
##  <a name="a-nameislockeda--cstringdataislocked"></a><a name="islocked"></a>CStringData::IsLocked  
 Bestimmt, ob die Zeichenpuffer gesperrt ist.  
  
```
bool IsLocked() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** , wenn der Puffer gesperrt; andernfalls ist **false**.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um zu bestimmen, ob ein Zeichenfolgenobjekt der Zeichenpuffer gesperrt ist.  
  
##  <a name="a-nameisshareda--cstringdataisshared"></a><a name="isshared"></a>CStringData::IsShared  
 Bestimmt, ob die Zeichenpuffer.  
  
```
bool IsShared() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** , wenn der Puffer freigegeben; andernfalls wird **false**.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um zu bestimmen, ob die Zeichenpuffer eines String-Objekts von mehreren String-Objekten gegenwärtig freigegeben ist.  
  
##  <a name="a-namelocka--cstringdatalock"></a><a name="lock"></a>CStringData::Lock  
 Sperrt den Zeichenpuffer zugeordnete String-Objekt.  
  
```
void Lock() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um den Zeichenpuffer des String-Objekts zu sperren. Sperren und entsperren wird verwendet, wenn der Entwickler direkter Zugriff auf den Zeichenpuffer erforderlich ist. Ein gutes Beispiel für Sperren wird veranschaulicht, durch die [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) und [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) Methoden der `CSimpleStringT`.  
  
> [!NOTE]
>  Ein Zeichenpuffer kann nur gesperrt werden, falls der Puffer in höhere Zeichenfolgenobjekte nicht freigegeben wird.  
  
##  <a name="a-namenalloclengtha--cstringdatanalloclength"></a><a name="nalloclength"></a>CStringData::nAllocLength  
 Die Länge des Zeichenpuffers reservierte.  
  
```
int nAllocLength;
```  
  
### <a name="remarks"></a>Hinweise  
 Speichert die Länge des Datenpuffers zugeordneten in `XCHAR`s (einschließlich abschließenden Nullzeichen).  
  
##  <a name="a-namendatalengtha--cstringdatandatalength"></a><a name="ndatalength"></a>CStringData::nDataLength  
 Aktuelle Länge der String-Objekt.  
  
```
int nDataLength;
```  
  
### <a name="remarks"></a>Hinweise  
 Speichert die Länge der aktuell verwendeten Daten in `XCHAR`s (einschließlich abschließenden Nullzeichen).  
  
##  <a name="a-namenrefsa--cstringdatanrefs"></a><a name="nrefs"></a>CStringData::nRefs  
 Der Verweiszähler des String-Objekts.  
  
```
long nRefs;
```  
  
### <a name="remarks"></a>Hinweise  
 Speichert den Verweiszähler des String-Objekts. Dieser Zähler gibt die Anzahl der Zeichenfolgenobjekte der höheren, die das Datenobjekt Zeichenfolge zugeordnet sind. Ein negativer Wert gibt an, dass das Datenobjekt Zeichenfolge derzeit gesperrt ist.  
  
##  <a name="a-namepstringmgra--cstringdatapstringmgr"></a><a name="pstringmgr"></a>CStringData::pStringMgr  
 Der Speicher-Manager des zugeordneten Objekts.  
  
```
IAtlStringMgr* pStringMgr;
```  
  
### <a name="remarks"></a>Hinweise  
 Speichert die Speicher-Manager für das Objekt zugeordnete Zeichenfolge. Weitere Informationen zu Speicher-Manager und Zeichenfolgen finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="a-namereleasea--cstringdatarelease"></a><a name="release"></a>CStringData::Release  
 Dekrementiert den Verweiszähler des String-Objekts.  
  
```
void Release() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können die dekrementiert des Verweiszählers Freigeben der `CStringData` Struktur, wenn der Verweiszähler&0; erreicht. Dies geschieht häufig, wenn ein String-Objekt wird gelöscht, und daher nicht mehr auf das Datenobjekt Zeichenfolge verweisen muss.  
  
 Der folgende Code würde aufrufen, z. B. `CStringData::Release` für das Datenobjekt Zeichenfolge zugeordneten `str1`:  
  
 [!code-cpp[NVC_ATLMFC_Utilities&#104;](../../atl-mfc-shared/codesnippet/cpp/cstringdata-class_1.cpp)]  
  
##  <a name="a-nameunlocka--cstringdataunlock"></a><a name="unlock"></a>CStringData::Unlock  
 Entsperrt den Zeichenpuffer zugeordnete String-Objekt.  
  
```
void Unlock() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um den Zeichenpuffer Zeichenfolgenobjekt Daten zu entsperren. Sobald ein Puffer nicht gesperrt ist, kann freigegeben und Verweis gezählt werden kann.  
  
> [!NOTE]
>  Jeder Aufruf von `Lock` muss ein entsprechender Aufruf von übereinstimmende `Unlock`.  
  
 Sperren und entsperren wird verwendet, wenn der Entwickler muss sicherstellen, dass die Zeichenfolgen, die nicht freigegeben werden. Ein gutes Beispiel für Sperren wird veranschaulicht, durch die [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) und [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) Methoden der `CSimpleStringT`.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL/MFC-freigegeben Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)



