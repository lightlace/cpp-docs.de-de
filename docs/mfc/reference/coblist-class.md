---
title: CObList-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CObList
- AFXCOLL/CObList
- AFXCOLL/CObList::CObList
- AFXCOLL/CObList::AddHead
- AFXCOLL/CObList::AddTail
- AFXCOLL/CObList::Find
- AFXCOLL/CObList::FindIndex
- AFXCOLL/CObList::GetAt
- AFXCOLL/CObList::GetCount
- AFXCOLL/CObList::GetHead
- AFXCOLL/CObList::GetHeadPosition
- AFXCOLL/CObList::GetNext
- AFXCOLL/CObList::GetPrev
- AFXCOLL/CObList::GetSize
- AFXCOLL/CObList::GetTail
- AFXCOLL/CObList::GetTailPosition
- AFXCOLL/CObList::InsertAfter
- AFXCOLL/CObList::InsertBefore
- AFXCOLL/CObList::IsEmpty
- AFXCOLL/CObList::RemoveAll
- AFXCOLL/CObList::RemoveAt
- AFXCOLL/CObList::RemoveHead
- AFXCOLL/CObList::RemoveTail
- AFXCOLL/CObList::SetAt
dev_langs:
- C++
helpviewer_keywords:
- objects [C++], lists of
- CObList class
- lists, object
ms.assetid: 80699c93-33d8-4f8b-b8cf-7b58aeab64ca
caps.latest.revision: 20
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
ms.openlocfilehash: dc95f76be56f00f4779724facaf668a72b3d5ed6
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="coblist-class"></a>CObList-Klasse
sortierte Listen von nicht eindeutigen fSupports `CObject` Zeiger zugegriffen werden sequenziell oder über den Zeiger Wert.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CObList : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObList::CObList](#coblist)|Erstellt eine leere Liste für `CObject` Zeiger.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObList::AddHead](#addhead)|Fügt ein Element (oder alle Elemente in einer anderen Liste) an den Anfang der Liste (wird eine neue Head).|  
|[CObList::AddTail](#addtail)|Fügt ein Element (oder alle Elemente in einer anderen Liste) an das Ende der Liste (wird eine neue Erweiterung).|  
|[CObList::Find](#find)|Ruft die Position eines Elements durch Zeigerwert angegeben.|  
|[CObList::FindIndex](#findindex)|Ruft die Position eines Elements durch einen nullbasierten Index angegeben.|  
|[CObList::GetAt](#getat)|Ruft das Element an einer angegebenen Position ab.|  
|[CObList::GetCount](#getcount)|Gibt die Anzahl der Elemente in dieser Liste zurück.|  
|[CObList::GetHead](#gethead)|Gibt das Head-Element der Liste (darf nicht leer sein).|  
|[CObList::GetHeadPosition](#getheadposition)|Gibt die Position des Head-Element der Liste zurück.|  
|[CObList::GetNext](#getnext)|Ruft das nächste Element durchlaufen werden können.|  
|[CObList::GetPrev](#getprev)|Ruft das vorherige Element durchlaufen werden können.|  
|[CObList::GetSize](#getsize)|Gibt die Anzahl der Elemente in dieser Liste zurück.|  
|[CObList::GetTail](#gettail)|Gibt das Ende der Liste (darf nicht leer sein) zurück.|  
|[CObList::GetTailPosition](#gettailposition)|Gibt die Position des Elements Ende der Liste.|  
|[CObList::InsertAfter](#insertafter)|Fügt ein neues Element nach einer angegebenen Position ein.|  
|[CObList::InsertBefore](#insertbefore)|Fügt vor einer angegebenen Position ein neues Element.|  
|[CObList::IsEmpty](#isempty)|Tests für die leere Liste Bedingung (keine Elemente).|  
|[CObList::RemoveAll](#removeall)|Entfernt alle Elemente aus dieser Liste.|  
|[CObList::RemoveAt](#removeat)|Entfernt ein Element aus dieser Liste anhand der Position angegeben.|  
|[CObList::RemoveHead](#removehead)|Entfernt das Element am Anfang der Liste.|  
|[CObList::RemoveTail](#removetail)|Entfernt das Element dem Ende der Liste aus.|  
|[CObList::SetAt](#setat)|Legt das Element an einer bestimmten Position fest.|  
  
## <a name="remarks"></a>Hinweise  
 `CObList`Listen Verhalten sich wie doppelt verknüpfte Listen.  
  
 Eine Variable vom Typ **POSITION** ist ein Schlüssel für die Liste. Sie können eine **POSITION** Variable als einen Iterator für eine Liste sequenziell zu durchlaufen und als ein Lesezeichen an einen Ort zu speichern. Eine Position ist identisch mit einem Index jedoch nicht.  
  
 Element einfügen ist sehr schnell an den Listenanfang am Ende und an einem bekannten **POSITION**. Eine sequenzielle Suche ist erforderlich, um ein Element nach Wert oder Index zu suchen. Diese Suche kann lange dauern, wenn die Liste lang ist.  
  
 `CObList`enthält die `IMPLEMENT_SERIAL` Makro zur Unterstützung der Serialisierung und Sicherung der Elemente. Wenn eine Liste der `CObject` Zeiger gespeichert ist, in ein Archiv, das entweder mit einem überladenen Operator zum Einfügen oder mit der `Serialize` Member-Funktion, `CObject` Element wiederum serialisiert wird.  
  
 Wenn Sie eine Sicherung der einzelnen benötigen `CObject` Elemente in der Liste, müssen Sie die Tiefe des sicherungskontexts auf 1 oder größer festlegen.  
  
 Wenn ein `CObList` Objekt gelöscht wird oder wenn dessen Elemente entfernt werden, nur die `CObject` Zeiger entfernt wurden, nicht die Objekte, die sie verweisen.  
  
 Sie können Ihre eigenen Klassen ableiten `CObList`. Die neue Listenklasse, entwickelt für Zeiger auf Objekte, die von abgeleiteten `CObject`, neue Datenelemente und neuen Memberfunktionen hinzugefügt. Beachten Sie, dass die resultierende Liste nicht streng typsicher ist, weil dadurch eine Einfügung `CObject` Zeiger.  
  
> [!NOTE]
>  Verwenden Sie die [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) Makro in der Implementierung von der abgeleiteten Klasse, wenn Sie beabsichtigen, die Liste zu serialisieren.  
  
 Weitere Informationen zur Verwendung von `CObList`, finden Sie im Artikel [Sammlungen](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CObList`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcoll.h  
  
##  <a name="addhead"></a>CObList::AddHead  
 Fügt ein neues Element oder eine Liste von Elementen an den Anfang der Liste.  
  
```  
POSITION AddHead(CObject* newElement);  
void AddHead(CObList* pNewList);
```  
  
### <a name="parameters"></a>Parameter  
 `newElement`  
 Die `CObject` Zeiger auf dieser Liste hinzugefügt werden.  
  
 `pNewList`  
 Ein Zeiger auf einen anderen `CObList` Liste. Die Elemente in `pNewList` wird zu dieser Liste hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die erste Version der **POSITION** Wert des neu eingefügten Element.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::AddHead`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSITION AddHead (void\* ** `newElement` **);**<br /><br /> **void AddHead (CPtrList\* ** `pNewList` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION AddHead (const CString &** `newElement` **);**<br /><br /> **POSITION AddHead (LPCTSTR** `newElement` **);**<br /><br /> **void AddHead (CStringList\* ** `pNewList` **);**|  
  
### <a name="remarks"></a>Hinweise  
 Die Liste kann leer ist, bevor der Vorgang sein.  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CObList::CObList](#coblist) eine Liste der `CAge` Klasse.  
  
 [!code-cpp[NVC_MFCCollections&#89;](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt:  
  
 `AddHead example: A CObList with 2 elements`  
  
 `a CAge at $44A8 40`  
  
 `a CAge at $442A 21`  
  
##  <a name="addtail"></a>CObList::AddTail  
 Fügt ein neues Element oder eine Liste von Elementen an das Ende der Liste.  
  
```  
POSITION AddTail(CObject* newElement);  
void AddTail(CObList* pNewList);
```  
  
### <a name="parameters"></a>Parameter  
 `newElement`  
 Die `CObject` Zeiger auf dieser Liste hinzugefügt werden.  
  
 `pNewList`  
 Ein Zeiger auf einen anderen `CObList` Liste. Die Elemente in `pNewList` wird zu dieser Liste hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die erste Version der **POSITION** Wert des neu eingefügten Element.  
  
### <a name="remarks"></a>Hinweise  
 Die Liste kann leer ist, bevor der Vorgang sein.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::AddTail`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSITION AddTail (void\* ** `newElement` **);**<br /><br /> **void AddTail (CPtrList\* ** `pNewList` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION AddTail (const CString &** `newElement` **);**<br /><br /> **POSITION AddTail (LPCTSTR** `newElement` **);**<br /><br /> **void AddTail (CStringList\* ** `pNewList` **);**|  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CObList::CObList](#coblist) eine Liste der `CAge` Klasse.  
  
 [!code-cpp[NVC_MFCCollections&#90;](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt:  
  
 `AddTail example: A CObList with 2 elements`  
  
 `a CAge at $444A 21`  
  
 `a CAge at $4526 40`  
  
##  <a name="coblist"></a>CObList::CObList  
 Erstellt ein leeres `CObject` Zeiger Liste.  
  
```  
CObList(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>Parameter  
 `nBlockSize`  
 Die Granularität der speicherbelegung zum Erweitern der Liste.  
  
### <a name="remarks"></a>Hinweise  
 Je umfangreicher die Liste wird in Einheiten von Arbeitsspeicher zugeordnet `nBlockSize` Einträge. Wenn eine speicherbelegung fehlschlägt, eine `CMemoryException` ausgelöst.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::CObList`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**CPtrList (INT_PTR** `nBlockSize` **= 10);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CStringList (INT_PTR** `nBlockSize` **= 10);**|  
  
### <a name="example"></a>Beispiel  
  Im folgenden finden Sie eine Liste der `CObject`-abgeleitete Klasse `CAge` in die Auflistung Beispiele verwendet:  
  
 [!code-cpp[NVC_MFCCollections&#91;](../../mfc/codesnippet/cpp/coblist-class_3.h)]  
  
 Im folgenden finden Sie ein Beispiel für `CObList` Konstruktor Verwendung:  
  
 [!code-cpp[NVC_MFCCollections&#92;](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]  
  
##  <a name="find"></a>CObList::Find  
 Sucht die Liste sequenziell nach der ersten `CObject` Zeiger, die mit dem angegebenen `CObject` Zeiger.  
  
```  
POSITION Find(
    CObject* searchValue,  
    POSITION startAfter = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `searchValue`  
 Der Zeiger des Objekts in der Liste gefunden werden.  
  
 `startAfter`  
 Die Startposition für die Suche.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** -Wert, der für die Iteration oder Abrufen von Objekten Zeiger; verwendet werden kann **NULL** , wenn das Objekt nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass der Zeigerwerte verglichen werden, nicht den Inhalt der Objekte.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::Find`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Suchen der POSITION (void\* ** `searchValue` **, POSITION** `startAfter` **= NULL) const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Suchen der POSITION (LPCTSTR** `searchValue` **, POSITION** `startAfter` **= NULL) const;**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](#coblist) eine Liste der `CAge` Klasse.  
  
 [!code-cpp[NVC_MFCCollections&#93;](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]  
  
##  <a name="findindex"></a>CObList::FindIndex  
 Verwendet den Wert der `nIndex` als Index in der Liste.  
  
```  
POSITION FindIndex(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der nullbasierte Index des Listenelements gefunden werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** -Wert, der für die Iteration oder Abrufen von Objekten Zeiger; verwendet werden kann **NULL** Wenn `nIndex` ist zu groß. (Das Framework generiert eine Assertion, wenn `nIndex` negativ ist.)  
  
### <a name="remarks"></a>Hinweise  
 Am Anfang der Liste beenden auf einen sequenziellen Scan Starten der *n*th-Element.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::FindIndex`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**FindIndex POSITION (INT_PTR** `nIndex` **) const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**FindIndex POSITION (INT_PTR** `nIndex` **) const;**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](#coblist) eine Liste der `CAge` Klasse.  
  
 [!code-cpp[NVC_MFCCollections&#94;](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]  
  
##  <a name="getat"></a>CObList::GetAt  
 Eine Variable vom Typ **POSITION** ist ein Schlüssel für die Liste.  
  
```  
CObject*& GetAt(POSITION position);  
const CObject*& GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *Position*  
 Ein **POSITION** von einem vorherigen zurückgegebene Wert `GetHeadPosition` oder **suchen** Member-Funktionsaufruf.  
  
### <a name="return-value"></a>Rückgabewert  
 Finden Sie in der Beschreibung Rückgabewert [GetHead](#gethead).  
  
### <a name="remarks"></a>Hinweise  
 Es ist nicht identisch mit einem Index, und Sie können nicht ausgeführt werden, auf eine **POSITION** Wert selbst. `GetAt`Ruft die `CObject` Zeiger, die einer bestimmten Position zugeordnet.  
  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert eine gültige Position in der Liste darstellt. Wenn sie ungültig ist, überprüft dann die Debugversion der Microsoft Foundation Class-Bibliothek.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::GetAt`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const Void\*& GetAt (POSITION** *Position* **) const;**<br /><br /> **void\*& GetAt (POSITION** *Position* **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetAt (POSITION** *Position* **) const;**<br /><br /> **CString- & GetAt (POSITION** *Position* **);**|  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [FindIndex](#findindex).  
  
##  <a name="getcount"></a>CObList::GetCount  
 Ruft die Anzahl der Elemente in dieser Liste.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, die die Anzahl der Elemente enthält.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::GetCount`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetCount () const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetCount () const;**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](#coblist) eine Liste der `CAge` Klasse.  
  
 [!code-cpp[NVC_MFCCollections&#95;](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]  
  
##  <a name="gethead"></a>CObList::GetHead  
 Ruft die `CObject` Zeiger, der das Head-Element der Liste darstellt.  
  
```  
CObject*& GetHead();  
const CObject*& GetHead() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Zugriff auf die Liste durch einen Zeiger auf eine **const CObList**, dann `GetHead` gibt eine `CObject` Zeiger. Dies kann die Funktion nur auf der rechten Seite einer zuweisungsanweisung verwendet werden, und schützt folglich aus die Liste.  
  
 Wenn die Liste zugegriffen wird, direkt oder über einen Zeiger auf eine `CObList`, dann `GetHead` gibt einen Verweis auf eine `CObject` Zeiger. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und daher Einträge in der Liste geändert werden.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf von `GetHead`. Wenn die Liste leer ist, überprüft dann die Version der Microsoft Foundation Class-Bibliothek. Verwendung [IsEmpty](#isempty) zu überprüfen, ob die Liste Elemente enthält.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::GetHead`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const Void\*& GetHead () const; void\*& GetHead ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetHead () const; CString- & GetHead ();**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](#coblist) eine Liste der `CAge` Klasse.  
  
 Das folgende Beispiel veranschaulicht die Verwendung von `GetHead` auf der linken Seite einer Zuweisung-Anweisung.  
  
 [!code-cpp[NVC_MFCCollections&#96;](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]  
  
##  <a name="getheadposition"></a>CObList::GetHeadPosition  
 Ruft die Position des Head-Element der Liste ab.  
  
```  
POSITION GetHeadPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** -Wert, der für die Iteration oder Abrufen von Objekten Zeiger; verwendet werden kann **NULL** , wenn die Liste leer ist.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::GetHeadPosition`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Positionieren Sie GetHeadPosition (const).**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Positionieren Sie GetHeadPosition (const).**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](#coblist) eine Liste der `CAge` Klasse.  
  
 [!code-cpp[NVC_MFCCollections&#97;](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]  
  
##  <a name="getnext"></a>CObList::GetNext  
 Ruft das Listenelement identifizierten `rPosition`, legt dann `rPosition` auf dem `POSITION` Wert des nächsten Eintrag in der Liste.  
  
```  
CObject*& GetNext(POSITION& rPosition);  
const CObject* GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `rPosition`  
 Ein Verweis auf eine `POSITION` von einem vorherigen zurückgegebene Wert `GetNext`, `GetHeadPosition`, oder andere Member-Funktionsaufruf.  
  
### <a name="return-value"></a>Rückgabewert  
 Finden Sie in der Beschreibung Rückgabewert [GetHead](#gethead).  
  
### <a name="remarks"></a>Hinweise  
 Sie können `GetNext` in einer Iterationsschleife forward, wenn Sie die ursprüngliche Position mit einem Aufruf von einrichten `GetHeadPosition` oder `Find`.  
  
 Sie müssen sicherstellen, dass Ihre `POSITION` Wert eine gültige Position in der Liste darstellt. Wenn sie ungültig ist, überprüft dann die Debugversion der Microsoft Foundation Class-Bibliothek.  
  
 Wenn das abgerufene Element das letzte Element in der Liste der neue Wert des ist `rPosition` Wert `NULL`.  
  
 Es ist möglich, ein Element während einer Iteration zu entfernen. Siehe das Beispiel für [RemoveAt](#removeat).  
  
> [!NOTE]
>  Ab MFC 8.0 wurde die const Version dieser Methode geändert, um zurückgeben `const CObject*` anstelle von `const CObject*&`.  Diese Änderung wurde vorgenommen, um der Compiler in Übereinstimmung mit der C++-standard zu bringen.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::GetNext`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CObList::CObList](#coblist) eine Liste der `CAge` Klasse.  
  
 [!code-cpp[NVC_MFCCollections&#98;](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt:  
  
 `a CAge at $479C 40`  
  
 `a CAge at $46C0 21`  
  
##  <a name="getprev"></a>CObList::GetPrev  
 Ruft das Listenelement identifizierten `rPosition`, legt dann `rPosition` auf dem `POSITION` Wert des vorherigen Eintrags in der Liste.  
  
```  
CObject*& GetPrev(POSITION& rPosition);  
const CObject* GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `rPosition`  
 Ein Verweis auf eine `POSITION` von einem vorherigen zurückgegebene Wert `GetPrev` oder anderer Member-Funktionsaufruf.  
  
### <a name="return-value"></a>Rückgabewert  
 Finden Sie in der Beschreibung Rückgabewert [GetHead](#gethead).  
  
### <a name="remarks"></a>Hinweise  
 Sie können `GetPrev` in einer Schleife umgekehrte Iteration, wenn Sie die ursprüngliche Position mit einem Aufruf von einrichten `GetTailPosition` oder `Find`.  
  
 Sie müssen sicherstellen, dass Ihre `POSITION` Wert eine gültige Position in der Liste darstellt. Wenn sie ungültig ist, überprüft dann die Debugversion der Microsoft Foundation Class-Bibliothek.  
  
 Wenn das abgerufene Element der erste in der Liste dann den neuen Wert der `rPosition` Wert `NULL`.  
  
> [!NOTE]
>  Ab MFC 8.0 wurde die const Version dieser Methode geändert, um zurückgeben `const CObject*` anstelle von `const CObject*&`.  Diese Änderung wurde vorgenommen, um der Compiler in Übereinstimmung mit der C++-standard zu bringen.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::GetPrev`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CObList::CObList](#coblist) eine Liste der `CAge` Klasse.  
  
 [!code-cpp[NVC_MFCCollections&#99;](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt:  
  
 `a CAge at $421C 21`  
  
 `a CAge at $421C 40`  
  
##  <a name="getsize"></a>CObList::GetSize  
 Gibt die Anzahl der Elemente zurück.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der Liste.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Anzahl der Elemente in der Liste abzurufen.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::GetSize`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetSize () const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetSize () const;**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](#coblist) eine Liste der `CAge` Klasse.  
  
 [!code-cpp[NVC_MFCCollections&#100;](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]  
  
##  <a name="gettail"></a>CObList::GetTail  
 Ruft die `CObject` Zeiger, der das Ende Element dieser Liste darstellt.  
  
```  
CObject*& GetTail();  
const CObject*& GetTail() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Finden Sie in der Beschreibung Rückgabewert [GetHead](#gethead).  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf von `GetTail`. Wenn die Liste leer ist, überprüft dann die Version der Microsoft Foundation Class-Bibliothek. Verwendung [IsEmpty](#isempty) zu überprüfen, ob die Liste Elemente enthält.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::GetTail`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const Void\*& GetTail () const; void\*& GetTail ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetTail () const; CString- & GetTail ();**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](#coblist) eine Liste der `CAge` Klasse.  
  
 [!code-cpp[NVC_MFCCollections&#101;](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]  
  
##  <a name="gettailposition"></a>CObList::GetTailPosition  
 Ruft die Position des Elements Ende dieser Liste. **NULL** , wenn die Liste leer ist.  
  
```  
POSITION GetTailPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** -Wert, der für die Iteration oder Abrufen von Objekten Zeiger; verwendet werden kann **NULL** , wenn die Liste leer ist.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::GetTailPosition`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Positionieren Sie GetTailPosition (const).**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Positionieren Sie GetTailPosition (const).**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](#coblist) eine Liste der `CAge` Klasse.  
  
 [!code-cpp[NVC_MFCCollections&#102;](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]  
  
##  <a name="insertafter"></a>CObList::InsertAfter  
 Fügt ein Element dieser Liste nach dem Element an der angegebenen Position.  
  
```  
POSITION InsertAfter(
    POSITION position,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>Parameter  
 *Position*  
 Ein von einem früheren **,** oder einem Aufruf der `GetNext`Find `GetPrev`-Memberfunktion zurückgegebener Wert für **POSITION** .  
  
 `newElement`  
 Der Zeiger des Objekts zu dieser Liste hinzugefügt werden.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::InsertAfter`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSITION InsertAfter (POSITION** *Position* **, void\* ** `newElement` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION InsertAfter (POSITION** *Position* **, const CString &** `newElement` **);**<br /><br /> **POSITION InsertAfter (POSITION** *Position* **, LPCTSTR** `newElement` **);**|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** Wert, der die gleiche ist wie der *Position* Parameter.  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CObList::CObList](#coblist) eine Liste der `CAge` Klasse.  
  
 [!code-cpp[NVC_MFCCollections&#103;](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt:  
  
 `InsertAfter example: A CObList with 3 elements`  
  
 `a CAge at $4A44 40`  
  
 `a CAge at $4A64 65`  
  
 `a CAge at $4968 21`  
  
##  <a name="insertbefore"></a>CObList::InsertBefore  
 Fügt dieser Liste ein Element vor dem Element an der angegebenen Position hinzu.  
  
```  
POSITION InsertBefore(
    POSITION position,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>Parameter  
 *Position*  
 Ein von einem früheren **,** oder einem Aufruf der `GetNext`Find `GetPrev`-Memberfunktion zurückgegebener Wert für **POSITION** .  
  
 `newElement`  
 Der Zeiger des Objekts zu dieser Liste hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** -Wert, der für die Iteration oder Abrufen von Objekten Zeiger; verwendet werden kann **NULL** , wenn die Liste leer ist.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::InsertBefore`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**InsertBefore POSITION (POSITION** *Position* **, void\* ** `newElement` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**InsertBefore POSITION (POSITION** *Position* **, const CString &** `newElement` **);**<br /><br /> **InsertBefore POSITION (POSITION** *Position* **, LPCTSTR** `newElement` **);**|  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CObList::CObList](#coblist) eine Liste der `CAge` Klasse.  
  
 [!code-cpp[NVC_MFCCollections&#104;](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt:  
  
 `InsertBefore example: A CObList with 3 elements`  
  
 `a CAge at $4AE2 40`  
  
 `a CAge at $4B02 65`  
  
 `a CAge at $49E6 21`  
  
##  <a name="isempty"></a>CObList::IsEmpty  
 Gibt an, ob die Liste keine Elemente enthält.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn diese Liste ist leer. andernfalls 0.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::IsEmpty`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**BOOL IsEmpty () const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**BOOL IsEmpty () const;**|  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [RemoveAll](#removeall).  
  
##  <a name="removeall"></a>CObList::RemoveAll  
 Entfernt alle Elemente aus dieser Liste, und die zugeordnete freigegeben `CObList` Speicher.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie bereits die Liste leer ist, wird kein Fehler generiert.  
  
 Beim Entfernen von Elementen aus einem `CObList`, entfernen Sie die Objektzeiger aus der Liste. Es ist sicherstellen, dass Sie die Objekte selbst löschen.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::RemoveAll`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAll ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAll ();**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](#coblist) eine Liste der `CAge` Klasse.  
  
 [!code-cpp[NVC_MFCCollections&#105;](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]  
  
##  <a name="removeat"></a>CObList::RemoveAt  
 Entfernt das angegebene Element aus dieser Liste.  
  
```  
void RemoveAt(POSITION position);
```  
  
### <a name="parameters"></a>Parameter  
 *Position*  
 Die Position des Elements, das aus der Liste entfernt werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein Element Entfernen einer `CObList`, entfernen Sie den Zeiger aus der Liste. Es ist sicherstellen, dass Sie die Objekte selbst löschen.  
  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert eine gültige Position in der Liste darstellt. Wenn sie ungültig ist, überprüft dann die Debugversion der Microsoft Foundation Class-Bibliothek.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::RemoveAt`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAt (POSITION** *Position* **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAt (POSITION** *Position* **);**|  
  
### <a name="example"></a>Beispiel  
  Seien Sie vorsichtig beim Entfernen eines Elements während einer Iteration Liste. Das folgende Beispiel zeigt eine Entfernung Technik, die einen gültigen garantiert **POSITION** -Wert für [GetNext](#getnext).  
  
 Finden Sie unter [CObList::CObList](#coblist) eine Liste der `CAge` Klasse.  
  
 [!code-cpp[NVC_MFCCollections&#106;](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt:  
  
 `RemoveAt example: A CObList with 2 elements`  
  
 `a CAge at $4C1E 65`  
  
 `a CAge at $4B22 21`  
  
##  <a name="removehead"></a>CObList::RemoveHead  
 Entfernt das Element am Anfang der Liste, und gibt einen Zeiger darauf zurück.  
  
```  
CObject* RemoveHead();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die `CObject` Zeiger bereits am Anfang der Liste.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf von `RemoveHead`. Wenn die Liste leer ist, überprüft dann die Version der Microsoft Foundation Class-Bibliothek. Verwendung [IsEmpty](#isempty) zu überprüfen, ob die Liste Elemente enthält.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::RemoveHead`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* RemoveHead ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString-RemoveHead ();**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](#coblist) eine Liste der `CAge` Klasse.  
  
 [!code-cpp[NVC_MFCCollections&#107;](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]  
  
##  <a name="removetail"></a>CObList::RemoveTail  
 Entfernt das Element, das Ende der Liste aus, und gibt einen Zeiger darauf zurück.  
  
```  
CObject* RemoveTail();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Objekt, das am Ende der Liste wurde.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf von `RemoveTail`. Wenn die Liste leer ist, überprüft dann die Version der Microsoft Foundation Class-Bibliothek. Verwendung [IsEmpty](#isempty) zu überprüfen, ob die Liste Elemente enthält.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::RemoveTail`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* RemoveTail ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString-RemoveTail ();**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](#coblist) eine Liste der `CAge` Klasse.  
  
 [!code-cpp[NVC_MFCCollections&#108;](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]  
  
##  <a name="setat"></a>CObList::SetAt  
 Legt das Element an einer bestimmten Position fest.  
  
```  
void SetAt(
    POSITION pos,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Die **POSITION** des Elements festgelegt werden.  
  
 `newElement`  
 Die `CObject` Zeiger in der Liste geschrieben werden.  
  
### <a name="remarks"></a>Hinweise  
 Eine Variable vom Typ **POSITION** ist ein Schlüssel für die Liste. Es ist nicht identisch mit einem Index, und Sie können nicht ausgeführt werden, auf eine **POSITION** Wert selbst. `SetAt`Schreibt die `CObject` Zeiger auf der angegebenen Position in der Liste.  
  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert eine gültige Position in der Liste darstellt. Wenn sie ungültig ist, überprüft dann die Debugversion der Microsoft Foundation Class-Bibliothek.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObList::SetAt`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void SetAt (POSITION** `pos` **, const CString &** `newElement` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void SetAt( POSITION** `pos` **, LPCTSTR** `newElement` **);**|  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CObList::CObList](#coblist) eine Liste der `CAge` Klasse.  
  
 [!code-cpp[NVC_MFCCollections&#109;](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt:  
  
 `SetAt example: A CObList with 2 elements`  
  
 `a CAge at $4D98 40`  
  
 `a CAge at $4DB8 65`  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CStringList-Klasse](../../mfc/reference/cstringlist-class.md)   
 [CPtrList-Klasse](../../mfc/reference/cptrlist-class.md)

