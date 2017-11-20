---
title: Die Auflistungsklasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros.classes
dev_langs: C++
helpviewer_keywords:
- DestructElements function
- ConstructElements function
- SerializeElements function
- collection classes [MFC], helper functions
- helper functions collection class [MFC]
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b3d6baf4ba1622a9a9b54dcb25ed42eae89c86a0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="collection-class-helpers"></a>Hilfsfunktionen für die Auflistungsklasse
Die Auflistungsklassen `CMap`, `CList`, und `CArray` Hilfsvorlage globale Funktionen für Zwecke wie vergleichen, zum Kopieren und zum Serialisieren von Elementen verwenden. Als Teil der Implementierung von Klassen, die auf der Grundlage `CMap`, `CList`, und `CArray`, müssen Sie diese Funktionen bei Bedarf überschreiben, mit Versionen, die auf den Typ der Karte, Liste oder Array gespeicherten Daten zugeschnitten sind. Informationen zum Überschreiben von Hilfsfunktionen wie z. B. `SerializeElements`, finden Sie im Artikel [Sammlungen: Gewusst wie: Erstellen einer typsicheren Auflistung](../../mfc/how-to-make-a-type-safe-collection.md). Beachten Sie, dass **ConstructElements** und **DestructElements** sind veraltet.  
  
 Die Microsoft Foundation Class-Bibliothek bietet die folgenden globalen Funktionen in afxtempl.h beim Anpassen Ihrer Auflistungsklassen:  
  
### <a name="collection-class-helpers"></a>Hilfsfunktionen für die Auflistungsklasse  
  
|||  
|-|-|  
|[CompareElements](#compareelements)|Gibt an, ob Elemente identisch sind.|  
|[CopyElements](#copyelements)|Kopiert Elemente aus einem Array in eine andere.|  
|[DumpElements](#dumpelements)|Enthält die Diagnoseausgabe streamorientiertes.|  
|[HashKey](#hashkey)|Berechnet einen Hashschlüssel an.|  
|[SerializeElements](#serializeelements)|Speichert, oder ruft Elemente zu oder von einem Archiv ab.|  
  
##  <a name="compareelements"></a>CompareElements  
 Wird aufgerufen, direkt über [CList::Find] (Clist class.md #not_found.md #Clist__find und indirekt durch [Cmap__lookup](cmap-class.md#lookup) und [Cmap__operator &#91; &#93;](cmap-class.md#operator_at).  
  
```   
template<class TYPE, class ARG_TYPE>  
BOOL AFXAPI  
CompareElements(
    const TYPE* pElement1,  
    const ARG_TYPE* pElement2);  
```  
  
### <a name="parameters"></a>Parameter  
 *DATENTYP*  
 Der Typ des ersten Elements, das verglichen werden soll.  
  
 `pElement1`  
 Zeiger auf das erste Element, verglichen werden soll.  
  
 `ARG_TYPE`  
 Der Typ des zweiten Elements, das verglichen werden soll.  
  
 `pElement2`  
 Ein Zeiger auf das zweite Element verglichen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Objekt auf verweist `pElement1` ist gleich dem Objekt verweist, zu `pElement2`, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `CMap` ruft verwenden die `CMap` Vorlagenparameter *Schlüssel* und `ARG_KEY`.  
  
 Die Standardimplementierung gibt das Ergebnis des Vergleichs des  *\*pElement1* und  *\*pElement2*. Überschreiben Sie diese Funktion, sodass die Elemente in einer Weise verglichen wird, die für Ihre Anwendung geeignet ist.  
  
 Die Programmiersprache C++ definiert den Vergleichsoperator ( `==`) für einfache Typen ( `char`, `int`, **"float"**usw.), aber keinen Vergleichsoperator für Klassen und Strukturen definiert ist. Wenn Sie verwenden möchten `CompareElements` oder zum Instanziieren einer Auflistungsklasse, die verwendet werden, müssen Sie den Vergleichsoperator definieren oder überladen `CompareElements` mit einer Version, die entsprechenden Werte zurückgibt.  
  
### <a name="requirements"></a>Anforderungen  
   **Header:** afxtempl.h   
  
##  <a name="copyelements"></a>CopyElements  
 Diese Funktion wird aufgerufen, direkt über [CArray::Append](carray-class.md#append) und [CArray::Copy](carray-class.md#copy).  
  
```   
template<class TYPE>  
void AFXAPI CopyElements(
    TYPE* pDest,  
    const TYPE* pSrc,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Parameter  
 *DATENTYP*  
 Der Vorlagenparameter, der den Typ der zu kopierenden Elemente angibt.  
  
 `pDest`  
 Ein Zeiger auf das Ziel, die Elemente kopiert werden.  
  
 `pSrc`  
 Ein Zeiger auf die Quelle der zu kopierenden Elemente.  
  
 `nCount`  
 Anzahl der zu kopierenden Elemente.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung verwendet den einfache Zuweisungsoperator (  **=**  ) zum Ausführen des Kopiervorgangs. Wenn der Typ kopiert werden keinen überladenen Operator = die standardmäßige Implementierung führt eine bitweise Kopie.  
  
 Informationen zum Implementieren dieses und andere Hilfsfunktionen, finden Sie im Artikel [Sammlungen: Gewusst wie: Erstellen einer typsicheren Auflistung](../how-to-make-a-type-safe-collection.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxtempl.h  
  
##  <a name="dumpelements"></a>DumpElements  
 Die Elemente der Auflistung beim Überschreiben bereit streamorientiertes Diagnoseausgabe im Text-Format.  
  
```   
template<class TYPE>  
void  AFXAPI DumpElements(
    CDumpContext& dc,  
    const TYPE* pElements,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Parameter  
 `dc`  
 Kontext für das Sichern von Elementen zu speichern.  
  
 *DATENTYP*  
 Der Vorlagenparameter, der Typ der Elemente angibt.  
  
 `pElements`  
 Ein Zeiger auf die Elemente, die gesichert werden.  
  
 `nCount`  
 Die Anzahl von Elementen, die gesichert werden.  
  
### <a name="remarks"></a>Hinweise  
 Die **CArray::Dump**, **CList::Dump**, und **CMap::Dump** Funktionen aufrufen, wenn die Tiefe des Speicherabbilds größer als 0 ist.  
  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Wenn die Elemente der Auflistung abgeleitet sind `CObject`, Aufrufen die Außerkraftsetzung werden Elemente in der Auflistung, in der Regel durchlaufen. `Dump` für jedes Element im aktivieren.  
  

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
 Der Vorlagenparameter Angabe des Datentyps verwendet, um Zuordnungsschlüssel zugreifen.  
  
 `key`  
 Der Schlüssel, dessen Hashwert wird berechnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Hashwert des Schlüssels.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird aufgerufen, direkt über [CMap::RemoveKey](cmap-class.md#removekey) und indirekt durch [CMap::Lookup](cmap-class.md#lookup) und [CMap::Operator &#91; &#93;](cmap-class.md#operator_at).
  
 Die Standardimplementierung erstellt einen Hashwert, durch die Umstellung `key` um vier Positionen nach rechts. Überschreiben Sie diese Funktion, sodass Hashwerte für Ihre Anwendung geeignete zurückgegeben.  
  
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
 [CArray](carray-class.md), [CList](clist-class.md), und [CMap](cmap-class.md) mit dieser Funktion können Elemente serialisiert.  
  
```   
template<class TYPE>  
void AFXAPI SerializeElements(CArchive& ar, TYPE* pElements, INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Parameter  
 *DATENTYP*  
 Der Vorlagenparameter, der Typ der Elemente angibt.  
  
 `ar`  
 Ein Archivobjekt zum Archivieren in oder aus.  
  
 `pElements`  
 Ein Zeiger auf die Elemente, die archiviert.  
  
 `nCount`  
 Anzahl der Elemente, die archiviert  
  
### <a name="remarks"></a>Hinweise  
 Der Standardimplementierung wird eine bitweise lesen oder schreiben.  
  
 Informationen zum Implementieren dieses und andere Hilfsfunktionen, finden Sie im Artikel [Sammlungen: Gewusst wie: Erstellen einer typsicheren Auflistung](../how-to-make-a-type-safe-collection.md).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in den Artikel [Sammlungen: Gewusst wie: Erstellen einer typsicheren Auflistung](../how-to-make-a-type-safe-collection.md).  
 
### <a name="requirements"></a>Anforderungen  
  **Header** afxtempl.h 
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [CMap-Klasse](cmap-class.md)   
 [CList-Klasse](clist-class.md)   
 [CArray-Klasse](carray-class.md)