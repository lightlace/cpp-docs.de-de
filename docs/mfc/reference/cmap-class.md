---
title: CMap-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMap
- AFXTEMPL/CMap
- AFXTEMPL/CMap::CPair
- AFXTEMPL/CMap::CMap
- AFXTEMPL/CMap::GetCount
- AFXTEMPL/CMap::GetHashTableSize
- AFXTEMPL/CMap::GetNextAssoc
- AFXTEMPL/CMap::GetSize
- AFXTEMPL/CMap::GetStartPosition
- AFXTEMPL/CMap::InitHashTable
- AFXTEMPL/CMap::IsEmpty
- AFXTEMPL/CMap::Lookup
- AFXTEMPL/CMap::PGetFirstAssoc
- AFXTEMPL/CMap::PGetNextAssoc
- AFXTEMPL/CMap::PLookup
- AFXTEMPL/CMap::RemoveAll
- AFXTEMPL/CMap::RemoveKey
- AFXTEMPL/CMap::SetAt
dev_langs: C++
helpviewer_keywords:
- CMap [MFC], CPair
- CMap [MFC], CMap
- CMap [MFC], GetCount
- CMap [MFC], GetHashTableSize
- CMap [MFC], GetNextAssoc
- CMap [MFC], GetSize
- CMap [MFC], GetStartPosition
- CMap [MFC], InitHashTable
- CMap [MFC], IsEmpty
- CMap [MFC], Lookup
- CMap [MFC], PGetFirstAssoc
- CMap [MFC], PGetNextAssoc
- CMap [MFC], PLookup
- CMap [MFC], RemoveAll
- CMap [MFC], RemoveKey
- CMap [MFC], SetAt
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b745bb345377336377e46b9e49a45b340a2609b6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cmap-class"></a>CMap-Klasse
Eine Wörterbuchauflistungsklasse, die eindeutigen Schlüsseln Werte zuordnet.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject  
```  
  
#### <a name="parameters"></a>Parameter  
 `KEY`  
 Die Klasse des Objekts, das als Schlüssel für die Zuordnung verwendet.  
  
 `ARG` *_* `KEY`  
 Für verwendeten Datentyp `KEY` Argumente, in der Regel einen Verweis auf `KEY`.  
  
 `VALUE`  
 Die Klasse des Objekts in der Zuordnung gespeichert.  
  
 `ARG` *_* `VALUE`  
 Für verwendeten Datentyp `VALUE` Argumente, in der Regel einen Verweis auf `VALUE`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-structures"></a>Öffentliche Strukturen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMap::CPair](#cpair)|Eine geschachtelte Struktur mit einem Schlüssel-Wert und den Wert des zugeordneten Objekts.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMap::CMap](#cmap)|Erstellt eine Auflistung, die Schlüsseln Werte zuordnet.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMap::GetCount](#getcount)|Gibt die Anzahl der Elemente in dieser Zuordnung zurück.|  
|[CMap::GetHashTableSize](#gethashtablesize)|Gibt die Anzahl der Elemente in der Hashtabelle zurück.|  
|[CMap::GetNextAssoc](#getnextassoc)|Ruft das nächste Element für die Iteration an.|  
|[CMap::GetSize](#getsize)|Gibt die Anzahl der Elemente in dieser Zuordnung zurück.|  
|[CMap::GetStartPosition](#getstartposition)|Gibt die Position des ersten Elements zurück.|  
|[CMap::InitHashTable](#inithashtable)|Die Hashtabelle initialisiert, und gibt seine Größe an.|  
|[CMap::IsEmpty](#isempty)|Testet, ob die Bedingung leere Zuordnung (keine Elemente).|  
|[CMap::Lookup](#lookup)|Sucht einen bestimmten Schlüssel zugeordnete Wert.|  
|[CMap::PGetFirstAssoc](#pgetfirstassoc)|Gibt einen Zeiger auf das erste Element zurück.|  
|[CMap::PGetNextAssoc](#pgetnextassoc)|Ruft einen Zeiger auf das nächste Element für die Iteration an.|  
|[CMap::PLookup](#plookup)|Gibt einen Zeiger auf einen Schlüssel, dessen Wert dem angegebenen Wert übereinstimmt.|  
|[CMap::RemoveAll](#removeall)|Entfernt alle Elemente aus dieser Zuordnung.|  
|[CMap::RemoveKey](#removekey)|Entfernt ein Element mit einem Schlüssel angegeben.|  
|[CMap::SetAt](#setat)|Fügt ein Element in der Zuordnung; ersetzt ein vorhandenes Element, wenn ein übereinstimmender Schlüssel gefunden wird.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMap::operator]](#operator_at)|Fügt ein Element in der Zuordnung – Operator Ersatz für `SetAt`.|  
  
## <a name="remarks"></a>Hinweise  
 Nachdem Sie ein Schlüssel-Wert-Paar (Element) in die Zuordnung eingefügt haben, können Sie effizient abrufen oder löschen das Paar mit dem Schlüssel für den Zugriff darauf. Sie können auch alle Elemente in der Zuordnung durchlaufen.  
  
 Eine Variable vom Typ **POSITION** für den alternativen Zugriff auf Einträge verwendet wird. Sie können eine **POSITION** einen Eintrag "merken" sowie das Durchlaufen der Zuordnung. Sie können sich vorstellen, dass diese Iteration sequenzielle von Schlüssel-Wert ist; Es ist nicht. Die Sequenz von abgerufenen Elementen ist unbestimmt.  
  
 Bestimmte Memberfunktionen der Klasse Aufruf globale Hilfsfunktionen, die angepasst werden müssen, für die meisten Verwendungen von der `CMap` Klasse. Finden Sie unter [Auflistungsklasse](../../mfc/reference/collection-class-helpers.md) in Abschnitt Makros und Globals der `MFC Reference`.  
  
 `CMap`überschreibt [Einfügeoperatoren](../../mfc/reference/cobject-class.md#serialize) zur Unterstützung der Serialisierung laufzeittypenzugriff und zum Sichern der Elemente. Wenn eine Zuordnung mit einem Archiv gespeichert ist `Serialize`, jedes kartenelement wiederum serialisiert wird. Die standardmäßige Implementierung des der `SerializeElements` Hilfsfunktion wird eine bitweise schreiben. Für Informationen zur Serialisierung von sammelelementen Zeiger abgeleitet `CObject` oder andere benutzerdefinierte Typen finden Sie unter [Vorgehensweise: Erstellen einer typsicheren Auflistung](../../mfc/how-to-make-a-type-safe-collection.md).  
  
 Wenn Sie eine Diagnose Sicherung der einzelnen Elemente in der Zuordnung (die Schlüssel und Werte) benötigen, müssen Sie die Tiefe des sicherungskontexts auf 1 oder größer festlegen.  
  
 Wenn ein `CMap` Objekt gelöscht wird oder dessen Elemente entfernt werden, die Schlüssel und Werte werden entfernt.  
  
 Map-klassenableitung ähnelt Liste Ableitung. Finden Sie im Artikel [Sammlungen](../../mfc/collections.md) veranschaulicht die Ableitung von einem bestimmten Zweck ausgerichteter List-Klasse.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMap`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtempl.h  
  
##  <a name="cmap"></a>CMap::CMap  
 Erstellt eine leere Zuordnung.  
  
```  
CMap(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>Parameter  
 `nBlockSize`  
 Gibt die Granularität der speicherbelegung zum Erweitern der Zuordnung an.  
  
### <a name="remarks"></a>Hinweise  
 Wächst die Zuordnung wird Speicherplatz belegt in der Einheit `nBlockSize` Einträge.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#56](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]  
  
##  <a name="cpair"></a>CMap::CPair  
 Enthält ein Schlüssel-Wert und den Wert des zugeordneten Objekts.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine geschachtelte Struktur innerhalb der Klasse [CMap](../../mfc/reference/cmap-class.md).  
  
 Die Struktur besteht aus zwei Felder:  
  
- **Schlüssel** der tatsächliche Wert, der den Typ des Schlüssels.  
  
- **Wert** den Wert des zugeordneten Objekts.  
  
 Es wird verwendet, um die Rückgabewerte aus speichern [CMap::PLookup](#plookup), [CMap::PGetFirstAssoc](#pgetfirstassoc), und [CMap::PGetNextAssoc](#pgetnextassoc).  
  
### <a name="example"></a>Beispiel  
 Ein Beispiel der Verwendung finden Sie im Beispiel für [CMap::PLookup](#plookup).  
  
##  <a name="getcount"></a>CMap::GetCount  
 Ruft die Anzahl der Elemente in der Zuordnung ab.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMap::Lookup](#lookup).  
  
##  <a name="gethashtablesize"></a>CMap::GetHashTableSize  
 Bestimmt die Anzahl der Elemente in der Hashtabelle für die Karte an.  
  
```  
UINT GetHashTableSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der Hashtabelle.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#57](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]  
  
##  <a name="getnextassoc"></a>CMap::GetNextAssoc  
 Ruft das kartenelement auf `rNextPosition`, aktualisiert dann `rNextPosition` zum Verweisen auf das nächste Element in der Zuordnung.  
  
```  
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `rNextPosition`  
 Gibt einen Verweis auf eine **POSITION** von einem vorherigen zurückgegebene Wert `GetNextAssoc` oder `GetStartPosition` aufrufen.  
  
 *SCHLÜSSEL*  
 Vorlagenparameter, den Typ des Schlüssels der Zuordnung angibt.  
  
 `rKey`  
 Gibt an, der zurückgegebene Schlüssel des Elements abgerufen.  
  
 *WERT*  
 Der Vorlagenparameter, den Typ des Werts der Zuordnung angibt.  
  
 `rValue`  
 Gibt den zurückgegebenen Wert des abgerufenen Elements.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist besonders hilfreich für die Iteration durch alle Elemente in der Zuordnung. Beachten Sie, dass die Sequenz Position nicht notwendigerweise die Sequenz von Schlüssel-Wert identisch ist.  
  
 Wenn das abgerufene Element das letzte Element in der Zuordnung klicken Sie dann der neue Wert des `rNextPosition` festgelegt ist, um **NULL**.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMap::SetAt](#setat).  
  
##  <a name="getsize"></a>CMap::GetSize  
 Gibt die Anzahl der Elemente zurück.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der Zuordnung.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen der Anzahl von Elementen in der Zuordnung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="getstartposition"></a>CMap::GetStartPosition  
 Startet eine Iteration Zuordnung wird durch Zurückgeben einer **POSITION** -Wert, der übergeben werden kann eine `GetNextAssoc` aufrufen.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** Wert, der eine Startposition für die Karte; durchlaufen angibt oder **NULL** , wenn die Zuordnung leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Sequenz Iteration ist nicht vorhersagbar; Daher muss der "ersten Element in der Zuordnung" keine andere besonderen Bedeutung.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMap::SetAt](#setat).  
  
##  <a name="inithashtable"></a>CMap::InitHashTable  
 Initialisiert die Hashtabelle.  
  
```  
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUE);  
```  
  
### <a name="parameters"></a>Parameter  
 `hashSize`  
 Anzahl von Einträgen in der Hashtabelle.  
  
 `bAllocNow`  
 Wenn **"true"**, ordnet Sie die Hashtabelle, bei der Initialisierung; andernfalls wird die Tabelle zugeordnet, wenn erforderlich.  
  
### <a name="remarks"></a>Hinweise  
 Für optimale Leistung sollte die Hashtabellengröße eine Primzahl. Um Konflikte zu minimieren, sollten die Größe ungefähr 20 Prozent, die größer als das größte erwartete Dataset entsprechen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMap::Lookup](#lookup).  
  
##  <a name="isempty"></a>CMap::IsEmpty  
 Bestimmt, ob die Zuordnung leer ist.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn diese Zuordnung keine Elemente enthält; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMap::RemoveAll](#removeall).  
  
##  <a name="lookup"></a>CMap::Lookup  
 Sucht einen bestimmten Schlüssel zugeordnete Wert.  
  
```  
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `ARG_KEY`  
 Angabe des Typs der Vorlagenparameter der `key` Wert.  
  
 `key`  
 Gibt den Schlüssel, der identifiziert das Element gesucht werden soll.  
  
 *WERT*  
 Gibt den Typ des Werts gesucht werden soll.  
  
 `rValue`  
 Empfängt der gebundene Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Element gefunden wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 `Lookup`verwendet einen Hashalgorithmus auf um das kartenelement schnell mit einem Schlüssel zu suchen, die genau mit den angegebenen Schlüssel übereinstimmt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="operator_at"></a>CMap::operator]  
 Praktische Ersatz für die `SetAt` Memberfunktion.  
  
```  
VALUE& operator[](arg_key key);
```  
  
### <a name="parameters"></a>Parameter  
 *WERT*  
 Angeben des Datentyps für den Zuordnungswert Vorlagenparameter.  
  
 `ARG_KEY`  
 Der Vorlagenparameter, der Typ des Schlüsselwerts angibt.  
  
 `key`  
 Der Schlüssel, der zum Abrufen des Werts aus der Zuordnung verwendet wird.  
  
### <a name="remarks"></a>Hinweise  
 Daher kann er nur auf der linken Seite einer zuweisungsanweisung (ein l-Wert) verwendet werden. Wenn kein Map-Element mit dem angegebenen Schlüssel vorhanden ist, wird ein neues Element erstellt.  
  
 Es gibt keine "rechts" (r), die dieser Operator entspricht, da es besteht die Möglichkeit, die ein Schlüssel in der Zuordnung nicht gefunden werden kann. Verwenden der `Lookup` Member-Funktion für den Abruf von Listenelementen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMap::Lookup](#lookup).  
  
##  <a name="pgetfirstassoc"></a>CMap::PGetFirstAssoc  
 Gibt den ersten Eintrag der Map-Objekt zurück.  
  
```  
const CPair* PGetFirstAssoc() const; 
CPair* PGetFirstAssoc();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den ersten Eintrag in der Karte; finden Sie unter [CMap::CPair](#cpair). Wenn die Zuordnung wurden keine Einträge enthält, ist der Wert **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um einen Zeiger das erste Element in der Map-Objekt zurückzugeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#59](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]  
  
##  <a name="pgetnextassoc"></a>CMap::PGetNextAssoc  
 Ruft das kartenelement verweist `pAssocRec`.  
  
```  
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;  
  
CPair *PGetNextAssoc(const CPair* pAssocRet);
```  
  
### <a name="parameters"></a>Parameter  
 *pAssocRet*  
 Verweist auf einen Eintrag für die Zuordnung von einem vorherigen zurückgegebene [PGetNextAssoc](#pgetnextassoc) oder [CMap::PGetFirstAssoc](#pgetfirstassoc) aufrufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den nächsten Eintrag in der Karte; finden Sie unter [CMap::CPair](#cpair). Wenn das Element das letzte Element in der Zuordnung ist, ist der Wert **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum iterieren durch alle Elemente in der Zuordnung. Rufen Sie das erste Element mit einem Aufruf von `PGetFirstAssoc` und durchlaufen Sie dann auf der Karte mit aufeinander folgenden Aufrufen `PGetNextAssoc`.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMap::PGetFirstAssoc](#pgetfirstassoc).  
  
##  <a name="plookup"></a>CMap::PLookup  
 Sucht den Wert, der einen angegebenen Schlüssel zugeordnet ist.  
  
```  
const CPair* PLookup(ARG_KEY key) const;
CPair* PLookup(ARG_KEY key);  
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Schlüssel für das Element, nach dem gesucht werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf einen Schlüssel Struktur; finden Sie unter [CMap::CPair](#cpair). Wenn keine Übereinstimmung gefunden wird, `CMap::PLookup` gibt `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode für ein kartenelement mit einem Schlüssel zu suchen, die genau mit den angegebenen Schlüssel übereinstimmt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]  
  
##  <a name="removeall"></a>CMap::RemoveAll  
 Entfernt alle Werte aus dieser Zuordnung durch Aufrufen der globalen Hilfsfunktion **DestructElements**.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion funktioniert ordnungsgemäß, wenn die Zuordnung bereits leer ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]  
  
##  <a name="removekey"></a>CMap::RemoveKey  
 Sucht nach den Eintrag für die Zuordnung, die den bereitgestellten Schlüssel entspricht; Klicken Sie dann, wenn der Schlüssel gefunden wird, entfernt der Eintrag.  
  
```  
BOOL RemoveKey(ARG_KEY key);
```  
  
### <a name="parameters"></a>Parameter  
 `ARG_KEY`  
 Der Vorlagenparameter, der der Typ des Schlüssels angibt.  
  
 `key`  
 Schlüssel für das Element entfernt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Eintrag gefunden und erfolgreich entfernt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die **DestructElements** Hilfsfunktion wird verwendet, um den Eintrag zu entfernen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMap::SetAt](#setat).  
  
##  <a name="setat"></a>CMap::SetAt  
 Das primäre Mittel zum Einfügen eines Elements in einer Zuordnung.  
  
```  
void SetAt(ARG_KEY key, ARG_VALUE newValue);
```  
  
### <a name="parameters"></a>Parameter  
 `ARG_KEY`  
 Angabe des Typs der Vorlagenparameter der `key` Parameter.  
  
 `key`  
 Gibt den Schlüssel des neuen Elements.  
  
 `ARG_VALUE`  
 Angabe des Typs der Vorlagenparameter der `newValue` Parameter.  
  
 `newValue`  
 Gibt den Wert des neuen Elements.  
  
### <a name="remarks"></a>Hinweise  
 Zunächst wird der Schlüssel gesucht. Wenn der Schlüssel, gefunden wird und klicken Sie dann der entsprechende Wert geändert wird, Andernfalls wird ein neues Schlüssel-Wert-Paar erstellt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel erfassen](../../visual-cpp-samples.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)  
