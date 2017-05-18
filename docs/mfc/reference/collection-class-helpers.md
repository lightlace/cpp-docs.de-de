---
title: Die Auflistungsklasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- DestructElements function
- ConstructElements function
- SerializeElements function
- collection classes, helper functions
- helper functions collection class
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
caps.latest.revision: 14
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d2649ef9c8b0320a94ec28a2341baa0f768b07d0
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="collection-class-helpers"></a>Hilfsfunktionen für die Auflistungsklasse
Die Auflistungsklassen `CMap`, `CList`, und `CArray` auf Vorlagen basierende globale Hilfsfunktionen für Zwecke wie vergleichen, kopieren und Serialisieren von Elementen verwenden. Als Teil der Implementierung von Klassen, die auf der Grundlage der `CMap`, `CList`, und `CArray`, müssen Sie diese Funktionen bei Bedarf überschreiben, mit Versionen, die auf den Typ der in der Zuordnung, Liste oder Array gespeicherten Daten zugeschnitten sind. Informationen zum Überschreiben von Hilfsfunktionen wie z. B. `SerializeElements`, finden Sie im Artikel [Sammlungen: Gewusst wie: Erstellen einer typsicheren Auflistung](../../mfc/how-to-make-a-type-safe-collection.md). Beachten Sie, dass **ConstructElements** und **DestructElements** sind veraltet.  
  
 Die Microsoft Foundation Class-Bibliothek bietet die folgenden globalen Funktionen in afxtempl.h beim Anpassen Ihrer Auflistungsklassen:  
  
### <a name="collection-class-helpers"></a>Hilfsfunktionen für die Auflistungsklasse  
  
|||  
|-|-|  
|[CompareElements](#compareelements)|Gibt an, ob Elemente gleich sind.|  
|[CopyElements](#copyelements)|Kopiert Elemente aus einem Array in ein anderes.|  
|[DumpElements](#dumpelements)|Datenstromorientierten diagnostische Ausgabe liefert.|  
|[HashKey](#hashkey)|Berechnet einen Hashschlüssel.|  
|[SerializeElements](#serializeelements)|Speichert oder Elemente zu oder aus einem Archiv abgerufen.|  
  
##  <a name="compareelements"></a>CompareElements  
 Direkt vom namens [CList::Find] (Clist class.md #not_found.md #Clist__find und indirekt durch [Cmap__lookup](cmap-class.md#lookup) und [Cmap__operator []](cmap-class.md#operator_at).  
  
```   
template<class TYPE, class ARG_TYPE>  
BOOL AFXAPI  
CompareElements(
    const TYPE* pElement1,  
    const ARG_TYPE* pElement2);  
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Typ des ersten Elements verglichen werden soll.  
  
 `pElement1`  
 Ein Zeiger auf das erste Element verglichen werden soll.  
  
 `ARG_TYPE`  
 Der Typ des zweiten Elements verglichen werden soll.  
  
 `pElement2`  
 Ein Zeiger auf das zweite zu vergleichende Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Objekt zeigt `pElement1` ist gleich dem Objekt, das auf den `pElement2`; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `CMap` Ruft mithilfe der `CMap` Vorlagenparameter *Schlüssel* und `ARG_KEY`.  
  
 Die standardmäßige Implementierung gibt das Ergebnis des Vergleichs * \*pElement1* und * \*pElement2*. Überschreiben Sie diese Funktion, sodass die Elemente in einer Weise verglichen, die für Ihre Anwendung geeignet ist.  
  
 Die Programmiersprache C++ definiert den Vergleichsoperator ( `==`) für einfache Typen ( `char`, `int`, **Float**usw.), aber kein Vergleichsoperators für Klassen und Strukturen definiert. Wenn Sie verwenden möchten `CompareElements` oder zum Instanziieren eines Auflistungsklassen, der verwendet wird, müssen Sie definieren den Vergleichsoperator oder überladen `CompareElements` mit einer Version, die entsprechenden Werte zurückgibt.  
  
### <a name="requirements"></a>Anforderungen  
   **Header:** afxtempl.h   
  
##  <a name="copyelements"></a>CopyElements  
 Diese Funktion aufgerufen wird, direkt vom [CArray::Append](carray-class.md#append) und [CArray::Copy](carray-class.md#copy).  
  
```   
template<class TYPE>  
void AFXAPI CopyElements(
    TYPE* pDest,  
    const TYPE* pSrc,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Vorlagenparameter, der den zu kopierenden Elemente angibt.  
  
 `pDest`  
 Ein Zeiger auf das Ziel, die Elemente kopiert werden.  
  
 `pSrc`  
 Ein Zeiger auf die Quelle der zu kopierenden Elemente.  
  
 `nCount`  
 Anzahl der zu kopierenden Elemente.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung den einfache Zuweisungsoperator verwendet ( ** = ** ) zum Ausführen des Kopiervorgangs. Der Typ kopiert werden keinen überladenen Operator = die standardmäßige Implementierung eine bitweise Kopie führt.  
  
 Informationen zum Implementieren dieses und andere Hilfsfunktionen finden Sie im Artikel [Sammlungen: Gewusst wie: Erstellen einer typsicheren Auflistung](../how-to-make-a-type-safe-collection.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxtempl.h  
  
##  <a name="dumpelements"></a>DumpElements  
 Die Elemente der Auflistung beim Überschreiben bereit datenstromorientierten diagnostische Ausgabe in Textform.  
  
```   
template<class TYPE>  
void  AFXAPI DumpElements(
    CDumpContext& dc,  
    const TYPE* pElements,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Parameter  
 `dc`  
 Kontext für Elemente Dump-Sicherungen zu sichern.  
  
 *TYP*  
 Der Vorlagenparameter, die den Typ der Elemente.  
  
 `pElements`  
 Ein Zeiger auf die Elemente, die gesichert werden.  
  
 `nCount`  
 Die Anzahl der Elemente, die gesichert werden.  
  
### <a name="remarks"></a>Hinweise  
 Die **CArray::Dump**, **CList::Dump**, und **CMap::Dump** Funktionen aufrufen, wenn die Tiefe des Dumps größer als 0 ist.  
  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Wenn die Elemente der Auflistung abgeleitet wurden `CObject`, Aufrufen von überschreiben werden die Elemente der Auflistung, in der Regel durchlaufen. `Dump` für jedes Element im Gegenzug.  
  

### <a name="requirements"></a>Anforderungen  
  **Header** afxtempl.h  
  
##  <a name="hashkey"></a>HashKey  
 Berechnet einen Hashwert für den angegebenen Schlüssel.  
  
```  
template<class ARG_KEY>  
AFX_INLINE UINT AFXAPI HashKey(ARG_KEY  key); 
```  
  
### <a name="parameters"></a>Parameter  
 `ARG_KEY`  
 Angeben des-Datentyps verwendet, um die Karte Zugriffsschlüssel Vorlagenparameter.  
  
 `key`  
 Der Schlüssel, dessen Hashwert berechnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Hash-Wert des Schlüssels.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion aufgerufen wird, direkt vom [CMap::RemoveKey](cmap-class.md#removekey) und indirekt durch [CMap::Lookup](cmap-class.md#lookup) und [CMap::Operator []](cmap-class.md#operator_at).
  
 Die standardmäßige Implementierung erstellt einen Hashwert, durch die Verlagerung der `key` um vier Positionen nach rechts. Überschreiben Sie diese Funktion, sodass Hashwerte für Ihre Anwendung geeignete zurückgegeben.  
  
### <a name="example"></a>Beispiel
 ```cpp  
template <> UINT AFXAPI HashKey(unsigned __int64 key)
{
   // Generate the hash value by XORing the lower 32 bits of the number 
   // with the upper 32 bits
   return(UINT(key) ^ UINT(key >> 32));
}
 ```
 
### <a name="requirements"></a>Anforderungen  
  **Header** afxtempl.h 
  
##  <a name="serializeelements"></a>SerializeElements  
 [CArray](carray-class.md), [CList](clist-class.md), und [CMap](cmap-class.md) mit dieser Funktion können Sie Elemente serialisiert.  
  
```   
template<class TYPE>  
void AFXAPI SerializeElements(CArchive& ar, TYPE* pElements, INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Vorlagenparameter, die den Typ der Elemente.  
  
 `ar`  
 Ein Archivobjekt zum Archivieren von in oder aus.  
  
 `pElements`  
 Ein Zeiger auf die Elemente, die archiviert.  
  
 `nCount`  
 Anzahl der Elemente, die archiviert  
  
### <a name="remarks"></a>Hinweise  
 Der Standardimplementierung wird ein bitweises lesen oder schreiben.  
  
 Informationen zum Implementieren dieses und andere Hilfsfunktionen finden Sie im Artikel [Sammlungen: Gewusst wie: Erstellen einer typsicheren Auflistung](../how-to-make-a-type-safe-collection.md).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in diesem Artikel [Sammlungen: Gewusst wie: Erstellen einer typsicheren Auflistung](../how-to-make-a-type-safe-collection.md).  
 
### <a name="requirements"></a>Anforderungen  
  **Header** afxtempl.h 
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [CMap-Klasse](cmap-class.md)   
 [CList-Klasse](clist-class.md)   
 [CArray-Klasse](carray-class.md)
