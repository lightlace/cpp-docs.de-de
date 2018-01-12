---
title: CStringData Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringData
- ATLSIMPSTR/ATL::CStringData
- ATLSIMPSTR/ATL::AddRef
- ATLSIMPSTR/ATL::data
- ATLSIMPSTR/ATL::IsLocked
- ATLSIMPSTR/ATL::IsShared
- ATLSIMPSTR/ATL::Lock
- ATLSIMPSTR/ATL::Release
- ATLSIMPSTR/ATL::Unlock
- ATLSIMPSTR/ATL::nAllocLength
- ATLSIMPSTR/ATL::nDataLength
- ATLSIMPSTR/ATL::nRefs
- ATLSIMPSTR/ATL::pStringMgr
dev_langs: C++
helpviewer_keywords:
- CStringData class
- shared classes, CStringData
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7523ca52c0ded8ec9b3cf02dd6798beca8be5cf8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cstringdata-class"></a>CStringData-Klasse
Diese Klasse stellt die Daten von einem String-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```
struct CStringData
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[AddRef](#addref)|Inkrementiert den Verweiszähler des Datenobjekts Zeichenfolge an.|  
|[data](#data)|Ruft die Zeichendaten eines Zeichenfolgenobjekts ab.|  
|[IsLocked](#islocked)|Bestimmt, ob der Puffer des zugeordneten Objekts gesperrt ist.|  
|[IsShared](#isshared)|Bestimmt, ob der Puffer des zugeordneten Objekts derzeit gemeinsam verwendet wird.|  
|[Sperre](#lock)|Sperrt den Puffer des zugeordneten Objekts.|  
|[Version](#release)|Gibt das angegebene String-Objekt frei.|  
|[Entsperren](#unlock)|Entsperrt den Puffer des zugeordneten Objekts.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[nAllocLength](#nalloclength)|Länge der zugeordneten Daten in `XCHAR`s (nicht einschließlich abschließenden Nullzeichen)|  
|[nDataLength](#ndatalength)|Länge der aktuell verwendeten Daten in `XCHAR`s (nicht einschließlich abschließenden Nullzeichen)|  
|[nRefs](#nrefs)|Die aktuelle Verweisanzahl des Objekts.|  
|[pStringMgr](#pstringmgr)|Ein Zeiger auf die Zeichenfolgen-Manager von diesem String-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse sollte nur von Entwicklern zum Implementieren benutzerdefinierter Zeichenfolge-Managern verwendet werden. Weitere Informationen zu benutzerdefinierten Zeichenfolge-Managern, finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)  
  
 Diese Klasse kapselt die verschiedenen Typen von Informationen und Daten, die eine höhere String-Objekt zugeordnet sind, z. B. [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), oder [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md) -Objekte. Jede höhere String-Objekt, das einen Zeiger auf die zugehörigen `CStringData` Objekt, das mehrere Zeichenfolgenobjekten, zeigen Sie auf das gleiche Zeichenfolgenobjekt Daten ermöglicht. Diese Beziehung wird durch den Verweiszähler dieser Planergruppe dargestellt ( `nRefs`) von der `CStringData` Objekt.  
  
> [!NOTE]
>  In bestimmten Fällen kann ein String-Datentyp (z. B. **CFixedString**) ein Datenobjekt Zeichenfolge mit mehr als eine höhere String-Objekt wird nicht gemeinsam nutzen. Weitere Informationen dazu finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
 Diese Daten besteht aus:  
  
-   Der Speicher-Manager (des Typs [IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)) der Zeichenfolge.  
  
-   Die aktuelle Länge ( [nDataLength](#ndatalength)) der Zeichenfolge.  
  
-   Die zugeordnete Länge ( [nAllocLength](#nalloclength)) der Zeichenfolge. Aus Gründen der Leistung kann dies die aktuelle Zeichenfolgenlänge unterscheidet  
  
-   Die aktuelle Verweisanzahl ( [nRefs](#nrefs)) von der `CStringData` Objekt. Dieser Wert wird verwendet, bei der Bestimmung, wie viele Zeichenfolgenobjekten dem Freigeben von `CStringData` Objekt.  
  
-   Der Zeichenpuffer tatsächliche ( [Daten](#data)) der Zeichenfolge.  
  
    > [!NOTE]
    >  Der tatsächlichen Zeichenpuffer String-Objekt wird von der String-Manager zugeordnet und wird angefügt, um die `CStringData` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsimpstr.h  
  
##  <a name="addref"></a>CStringData::AddRef  
 Inkrementiert den Verweiszähler des String-Objekt.  
  
```
void AddRef() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Inkrementiert den Verweiszähler des String-Objekt.  
  
> [!NOTE]
>  Rufen Sie diese Methode nicht auf eine Zeichenfolge mit einer negativen Verweisanzahl, da eine negative Anzahl gibt an, dass der Zeichenfolgenpuffer gesperrt ist.  
  
##  <a name="data"></a>CStringData::data  
 Gibt einen Zeiger auf ein Zeichenfolgenobjekt, das der Zeichenpuffer.  
  
```
void* data() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den String-Objekt der Zeichenpuffer.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um den aktuellen Zeichenpuffer zugeordnete String-Objekt zurück.  
  
> [!NOTE]
>  Dieser Puffer ist nicht zugeordnet, durch die `CStringData` Objekt aber von der String-Manager bei Bedarf. Wenn zugeordnet ist, wird der Puffer auf das Datenobjekt Zeichenfolge angefügt.  
  
##  <a name="islocked"></a>CStringData::IsLocked  
 Bestimmt, ob der Zeichenpuffer gesperrt ist.  
  
```
bool IsLocked() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** ist der Puffer gesperrt ist andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um zu bestimmen, ob der Zeichenpuffer eines Zeichenfolgenobjekts gegenwärtig gesperrt ist.  
  
##  <a name="isshared"></a>CStringData::IsShared  
 Bestimmt, ob der Zeichenpuffer gemeinsam verwendet wird.  
  
```
bool IsShared() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn der Puffer, andernfalls freigegebenen ist **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um zu bestimmen, ob der Zeichenpuffer eines Zeichenfolgenobjekts für die Daten von mehreren Zeichenfolgenobjekten derzeit gemeinsam verwendet wird.  
  
##  <a name="lock"></a>CStringData::Lock  
 Sperrt der Zeichenpuffer zugeordnete String-Objekt.  
  
```
void Lock() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Sperren der Zeichenpuffer des Datenobjekts Zeichenfolge. Sperren und entsperren wird verwendet, wenn der Entwickler direkter Zugriff auf der Zeichenpuffer benötigen. Ein gutes Beispiel Sperren wird veranschaulicht, durch die [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) und [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) Methoden der `CSimpleStringT`.  
  
> [!NOTE]
>  Nur kann ein Zeichenpuffer gesperrt werden, wenn der Puffer nicht von der höheren Zeichenfolgenobjekten gemeinsam verwendet wird.  
  
##  <a name="nalloclength"></a>CStringData::nAllocLength  
 Die Länge des Zeichenpuffers reservierte.  
  
```
int nAllocLength;
```  
  
### <a name="remarks"></a>Hinweise  
 Speichert die Länge des Datenpuffers zugeordneten in `XCHAR`s (nicht einschließlich abschließenden Nullzeichen).  
  
##  <a name="ndatalength"></a>CStringData::nDataLength  
 Aktuelle Länge der String-Objekt.  
  
```
int nDataLength;
```  
  
### <a name="remarks"></a>Hinweise  
 Speichert die Länge der aktuell verwendeten Daten im `XCHAR`s (nicht einschließlich abschließenden Nullzeichen).  
  
##  <a name="nrefs"></a>CStringData::nRefs  
 Der Verweiszähler des Datenobjekts Zeichenfolge.  
  
```
long nRefs;
```  
  
### <a name="remarks"></a>Hinweise  
 Speichert den Verweiszähler des Datenobjekts Zeichenfolge an. Diese Zahl gibt die Anzahl der höheren Zeichenfolgenobjekten, die das Datenobjekt Zeichenfolge zugeordnet sind. Ein negativer Wert gibt an, dass das Datenobjekt Zeichenfolge zurzeit gesperrt ist.  
  
##  <a name="pstringmgr"></a>CStringData::pStringMgr  
 Der Speicher-Manager des zugeordneten Objekts.  
  
```
IAtlStringMgr* pStringMgr;
```  
  
### <a name="remarks"></a>Hinweise  
 Speichert die Speicher-Manager für das zugeordnete String-Objekt. Weitere Informationen zu Speicher-Manager und Zeichenfolgen finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="release"></a>CStringData::Release  
 Dekrementiert den Verweiszähler des Datenobjekts Zeichenfolge.  
  
```
void Release() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie den Verweiszähler verringern Freigeben der `CStringData` Struktur, wenn der Verweiszähler auf 0 (null) erreicht. Dies geschieht häufig, wenn ein String-Objekt gelöscht wird und muss daher nicht mehr auf das Datenobjekt Zeichenfolge verweisen.  
  
 Beispielsweise würde der folgende Code Aufrufen `CStringData::Release` für das Datenobjekt Zeichenfolge zugeordneten `str1`:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#104](../../atl-mfc-shared/codesnippet/cpp/cstringdata-class_1.cpp)]  
  
##  <a name="unlock"></a>CStringData::Unlock  
 Hebt die Sperre der Zeichenpuffer zugeordnete String-Objekt.  
  
```
void Unlock() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Entsperren der Zeichenpuffer des Datenobjekts Zeichenfolge. Wenn ein Puffer entsperrt ist, er freigegeben und Verweis gezählt werden kann.  
  
> [!NOTE]
>  Jeder Aufruf von `Lock` müssen durch einen entsprechenden Aufruf abgeglichen werden `Unlock`.  
  
 Sperren und entsperren wird verwendet, wenn der Entwickler muss sicherstellen, dass die Zeichenfolgendaten nicht gemeinsam verwendet werden. Ein gutes Beispiel Sperren wird veranschaulicht, durch die [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) und [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) Methoden der `CSimpleStringT`.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)


