---
title: Die Auflistungsklasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- DestructElements function
- ConstructElements function
- SerializeElements function
- collection classes [MFC], helper functions
- helper functions collection class [MFC]
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6607f70a18734310d184c5cdd05d1e87f1b82d35
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852346"
---
# <a name="collection-class-helpers"></a>Hilfsfunktionen für die Auflistungsklasse
Die Auflistungsklassen `CMap`, `CList`, und `CArray` Hilfsvorlage globale Funktionen für Zwecke wie vergleichen, kopieren und Serialisieren von Elementen verwenden. Als Teil der Implementierung von Klassen, die basierend auf `CMap`, `CList`, und `CArray`, Sie müssen diese Funktionen nach Bedarf außer Kraft setzen, mit Versionen, die auf den Typ der in Ihrer Zuordnung, Liste oder Array gespeicherten Daten zugeschnitten sind. Informationen zum Überschreiben von Hilfsfunktionen wie z. B. `SerializeElements`, finden Sie im Artikel [Sammlungen: wie eine typsichere Auflistung](../../mfc/how-to-make-a-type-safe-collection.md). Beachten Sie, dass `ConstructElements` und `DestructElements` sind veraltet.  
  
 Die Microsoft Foundation Class-Bibliothek bietet die folgenden globalen Funktionen in afxtempl.h können Sie Ihre Auflistungsklassen anpassen:  
  
### <a name="collection-class-helpers"></a>Hilfsfunktionen für die Auflistungsklasse  
  
|||  
|-|-|  
|[CompareElements](#compareelements)|Gibt an, ob Elemente gleich sind.|  
|[CopyElements](#copyelements)|Kopiert die Elemente aus einem Array in eine andere.|  
|[DumpElements](#dumpelements)|Stellt die Diagnoseausgabe Datenstrom-orientierten bereit.|  
|[HashKey](#hashkey)|Berechnet einen Hashschlüssel.|  
|[SerializeElements](#serializeelements)|Speichert, oder ruft die Elemente in oder aus einem Archiv ab.|  
  
##  <a name="compareelements"></a>  CompareElements  
 Wird aufgerufen, direkt von [CList::Find] (Clist-class.md #not_found.md #Clist__find und indirekt durch [Cmap__lookup](cmap-class.md#lookup) und [Cmap__operator &#91; &#93; ](cmap-class.md#operator_at).  
  
```   
template<class TYPE, class ARG_TYPE>  
BOOL AFXAPI  
CompareElements(
    const TYPE* pElement1,  
    const ARG_TYPE* pElement2);  
```  
  
### <a name="parameters"></a>Parameter  
 *TYPE*  
 Der Typ des ersten Elements, das verglichen werden soll.  
  
 *pElement1*  
 Zeiger auf das erste Element verglichen werden soll.  
  
 *ARG_TYPE*  
 Der Typ des zweiten Elements verglichen werden soll.  
  
 *pElement2*  
 Zeiger auf das zweite Element verglichen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Objekt, zeigt *pElement1* ist gleich dem Objekt verweist *pElement2*, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `CMap` aufruft, verwenden die `CMap` Vorlagenparameter *Schlüssel* und *ARG_KEY*.  
  
 Die Standardimplementierung gibt das Ergebnis des Vergleichs des  *\*pElement1* und  *\*pElement2*. Überschreiben Sie diese Funktion, sodass die Elemente in einer Weise miteinander verglichen, die für Ihre Anwendung geeignet ist.  
  
 Die Programmiersprache C++ definiert den Vergleichsoperator ( `==`) für einfache Typen (**Char**, **Int**, **"float"** und so weiter), aber einen Vergleichsoperator für nicht definiert Klassen und Strukturen. Wenn Sie verwenden möchten `CompareElements` oder um instanziieren eine Auflistungsklasse, die verwendet werden soll, müssen Sie definieren den Vergleichsoperator oder überladen `CompareElements` mit einer Version, die entsprechenden Werte zurückgibt.  
  
### <a name="requirements"></a>Anforderungen  
   **Header:** afxtempl.h   
  
##  <a name="copyelements"></a>  CopyElements  
 Diese Funktion wird aufgerufen, direkt vom [CArray::Append](carray-class.md#append) und [CArray::Copy](carray-class.md#copy).  
  
```   
template<class TYPE>  
void AFXAPI CopyElements(
    TYPE* pDest,  
    const TYPE* pSrc,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Parameter  
 *TYPE*  
 Template-Parameter, die den Typ des zu kopierenden Elemente angibt.  
  
 *pDest*  
 Zeiger auf das Ziel, in dem die Elemente kopiert werden.  
  
 *pSrc*  
 Zeiger auf die Quelle der zu kopierenden Elemente.  
  
 *nCount*  
 Anzahl der Elemente kopiert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung verwendet den einfache Zuweisungsoperator ( **=** ) um den Kopiervorgang auszuführen. Wenn der Typ, der kopiert werden kein überladenen Operators =, und klicken Sie dann die standardmäßige Implementierung eine bitweise Kopie führt.  
  
 Informationen zum Implementieren dieses und andere Hilfsfunktionen finden Sie im Artikel [Sammlungen: wie eine typsichere Auflistung](../how-to-make-a-type-safe-collection.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxtempl.h  
  
##  <a name="dumpelements"></a>  DumpElements  
 Stellt den Datenstrom-orientierten Diagnoseausgabe im Text-Format für die Elemente der Auflistung Ruft beim Überschreiben bereit.  
  
```   
template<class TYPE>  
void  AFXAPI DumpElements(
    CDumpContext& dc,  
    const TYPE* pElements,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Parameter  
 *dc*  
 Sichern von Kontext zum Abrufen von Elementen.  
  
 *TYPE*  
 Template-Parameter, die den Typ der Elemente angibt.  
  
 *pElements*  
 Zeiger auf Elemente, die gesichert werden.  
  
 *nCount*  
 Die Anzahl von Elementen, die gesichert werden.  
  
### <a name="remarks"></a>Hinweise  
 Die `CArray::Dump`, `CList::Dump`, und `CMap::Dump` Funktionen aufrufen, wenn die Tiefe des Dumps größer als 0 ist.  
  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Wenn die Elemente der Sammlung von abgeleitet werden `CObject`, aufrufen Ihre Überschreibung werden Elemente in der Auflistung, in der Regel durchlaufen. `Dump` für jedes Element in aktivieren.  
  

### <a name="requirements"></a>Anforderungen  
  **Header** afxtempl.h  
  
##  <a name="hashkey"></a>  HashKey  
 Berechnet einen Hashwert für den angegebenen Schlüssel.  
  
```  
template<class ARG_KEY>  
AFX_INLINE UINT AFXAPI HashKey(ARG_KEY  key); 
```  
  
### <a name="parameters"></a>Parameter  
 *ARG_KEY*  
 Der Vorlagenparameter, der den Datentyp für den Zugriff auf Zuordnungsschlüssel angeben.  
  
 *key*  
 Der Schlüssel, dessen Hashwert berechnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Hash-Wert des Schlüssels.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird aufgerufen, direkt vom [CMap::RemoveKey](cmap-class.md#removekey) und indirekt durch [CMap::Lookup](cmap-class.md#lookup) und [CMap::Operator &#91; &#93; ](cmap-class.md#operator_at).
  
 Die Standardimplementierung erstellt einen Hashwert, durch die Umstellung *Schlüssel* um vier Positionen nach rechts. Überschreiben Sie diese Funktion, sodass Hashwerte für Ihre Anwendung geeignete zurückgegeben.  
  
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
  
##  <a name="serializeelements"></a>  SerializeElements  
 [CArray](carray-class.md), [CList](clist-class.md), und [CMap](cmap-class.md) mit dieser Funktion können Elemente serialisiert.  
  
```   
template<class TYPE>  
void AFXAPI SerializeElements(CArchive& ar, TYPE* pElements, INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Parameter  
 *TYPE*  
 Template-Parameter, die den Typ der Elemente angibt.  
  
 *ar*  
 Ein Archivobjekt zum Archivieren von in oder aus.  
  
 *pElements*  
 Zeiger auf die Elemente, die archiviert werden.  
  
 *nCount*  
 Anzahl der Elemente, die archiviert werden  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung ist eine bitweise lesen oder schreiben.  
  
 Informationen zum Implementieren dieses und andere Hilfsfunktionen finden Sie im Artikel [Sammlungen: wie eine typsichere Auflistung](../how-to-make-a-type-safe-collection.md).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in diesem Artikel [Sammlungen: wie eine typsichere Auflistung](../how-to-make-a-type-safe-collection.md).  
 
### <a name="requirements"></a>Anforderungen  
  **Header** afxtempl.h 
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [CMap-Klasse](cmap-class.md)   
 [CList-Klasse](clist-class.md)   
 [CArray-Klasse](carray-class.md)