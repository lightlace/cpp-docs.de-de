---
title: CMapStringToOb-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMapStringToOb
- AFXCOLL/CMapStringToOb
- AFXCOLL/CMapStringToOb::CMapStringToOb
- AFXCOLL/CMapStringToOb::GetCount
- AFXCOLL/CMapStringToOb::GetHashTableSize
- AFXCOLL/CMapStringToOb::GetNextAssoc
- AFXCOLL/CMapStringToOb::GetSize
- AFXCOLL/CMapStringToOb::GetStartPosition
- AFXCOLL/CMapStringToOb::HashKey
- AFXCOLL/CMapStringToOb::InitHashTable
- AFXCOLL/CMapStringToOb::IsEmpty
- AFXCOLL/CMapStringToOb::Lookup
- AFXCOLL/CMapStringToOb::LookupKey
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CMapStringToOb [MFC], CMapStringToOb
- CMapStringToOb [MFC], GetCount
- CMapStringToOb [MFC], GetHashTableSize
- CMapStringToOb [MFC], GetNextAssoc
- CMapStringToOb [MFC], GetSize
- CMapStringToOb [MFC], GetStartPosition
- CMapStringToOb [MFC], HashKey
- CMapStringToOb [MFC], InitHashTable
- CMapStringToOb [MFC], IsEmpty
- CMapStringToOb [MFC], Lookup
- CMapStringToOb [MFC], LookupKey
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: 09653980-b885-4f3a-8594-0aeb7f94c601
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 52adc7ce08644fb002b2a0a2cd91d20d15d4f24a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375770"
---
# <a name="cmapstringtoob-class"></a>CMapStringToOb Class
Eine Wörterbuchauflistungsklasse, die eindeutige `CString` -Objekte und `CObject` -Zeiger einander zuordnet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMapStringToOb : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMapStringToOb::CMapStringToOb](#cmapstringtoob)|Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMapStringToOb::GetCount](#getcount)|Gibt die Anzahl der Elemente in dieser Zuordnung zurück.|  
|[CMapStringToOb::GetHashTableSize](#gethashtablesize)|Bestimmt die aktuelle Anzahl der Elemente in der Hashtabelle.|  
|[CMapStringToOb::GetNextAssoc](#getnextassoc)|Ruft das nächste Element für die Iteration an.|  
|[CMapStringToOb::GetSize](#getsize)|Gibt die Anzahl der Elemente in dieser Zuordnung zurück.|  
|[CMapStringToOb::GetStartPosition](#getstartposition)|Gibt die Position des ersten Elements zurück.|  
|[CMapStringToOb::HashKey](#hashkey)|Berechnet den Hashwert eines angegebenen Schlüssels.|  
|[CMapStringToOb::InitHashTable](#inithashtable)|Initialisiert die Hashtabelle.|  
|[CMapStringToOb::IsEmpty](#isempty)|Testet, ob die Bedingung leere Zuordnung (keine Elemente).|  
|[CMapStringToOb::Lookup](#lookup)|Sucht einen void-Zeiger auf der Grundlage der void-Zeiger-Schlüssels. Der Wert des Zeigers, nicht auf die Entität, die es verweist, wird für Schlüsselvergleich verwendet.|  
|[CMapStringToOb::LookupKey](#lookupkey)|Gibt einen Verweis auf den zugeordneten Schlüssel für das angegebene Schlüssel-Wert zurück.|  
|[CMapStringToOb::RemoveAll](#removeall)|Entfernt alle Elemente aus dieser Zuordnung.|  
|[CMapStringToOb::RemoveKey](#removekey)|Entfernt ein Element mit einem Schlüssel angegeben.|  
|[CMapStringToOb::SetAt](#setat)|Fügt ein Element in der Zuordnung; ersetzt ein vorhandenes Element, wenn ein übereinstimmender Schlüssel gefunden wird.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMapStringToOb::operator]](#operator_at)|Fügt ein Element in der Zuordnung – Operator Ersatz für `SetAt`.|  
  
## <a name="remarks"></a>Hinweise  
 Nachdem Sie eingefügt haben eine `CString` -  `CObject*` Paar (Element) in der Zuordnung können Sie effizient abrufen oder löschen das Paar, das mit einer Zeichenfolge oder ein `CString` Wert als Schlüssel. Sie können auch alle Elemente in der Zuordnung durchlaufen.  
  
 Eine Variable vom Typ **POSITION** für den Zugriff der alternative Eintrag in allen Varianten der Zuordnung verwendet wird. Sie können eine **POSITION** einen Eintrag "merken" sowie das Durchlaufen der Zuordnung. Sie können sich vorstellen, dass diese Iteration sequenzielle von Schlüssel-Wert ist; Es ist nicht. Die Sequenz von abgerufenen Elementen ist unbestimmt.  
  
 `CMapStringToOb` enthält die `IMPLEMENT_SERIAL` -Makro für die Unterstützung von Serialisierung laufzeittypenzugriff und zum Sichern der Elemente. Wiederum jedes Element serialisiert wird, wenn eine Zuordnung zu einem Archiv, entweder mit den überladenen einfügen gespeichert ist ( **<<**) Operator oder mit der `Serialize` Memberfunktion.  
  
 Wenn Sie eine Diagnose Sicherung der einzelnen Elemente in der Zuordnung benötigen (die `CString` Wert und die `CObject` Inhalt), müssen Sie die Tiefe des sicherungskontexts auf 1 oder größer festlegen.  
  
 Wenn eine `CMapStringToOb` Objekt gelöscht wird oder wenn dessen Elemente entfernt werden, die `CString` Objekte und die `CObject` zeigenden Elemente entfernt werden. Die Objekte, auf die verwiesen wird durch die `CObject` Zeigern werden nicht zerstört.  
  
 Map-klassenableitung ähnelt Liste Ableitung. Finden Sie im Artikel [Sammlungen](../../mfc/collections.md) veranschaulicht die Ableitung von einem bestimmten Zweck ausgerichteter List-Klasse.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToOb`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcoll.h  
  
##  <a name="cmapstringtoob"></a>  CMapStringToOb::CMapStringToOb  
 Erstellt ein leeres `CString`- zu - `CObject*` zuordnen.  
  
```  
CMapStringToOb(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>Parameter  
 `nBlockSize`  
 Gibt die Granularität der speicherbelegung zum Erweitern der Zuordnung an.  
  
### <a name="remarks"></a>Hinweise  
 Wächst die Zuordnung wird Speicherplatz belegt in der Einheit `nBlockSize` Einträge.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind **CMapStringToOb:: CMapStringToOb**.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**CMapPtrToPtr( INT_PTR** `nBlockSize` **= 10 );**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**CMapPtrToWord( INT_PTR** `nBlockSize` **= 10 );**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**CMapStringToPtr( INT_PTR** `nBlockSize` **= 10 );**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CMapStringToString( INT_PTR** `nBlockSize` **= 10 );**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CMapWordToOb( INT_PTR** `nBlockSize` **= 10 );**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**MapWordToPtr (INT_PTR** `nBlockSize` **= 10);**|  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#63](../../mfc/codesnippet/cpp/cmapstringtoob-class_1.cpp)]  
  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) für eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
##  <a name="getcount"></a>  CMapStringToOb::GetCount  
 Bestimmt, wie viele Elemente in der Zuordnung sind.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in dieser Zuordnung.  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::GetCount`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetCount( ) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetCount( ) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetCount( ) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetCount( ) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetCount( ) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetCount( ) const;**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) für eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections#64](../../mfc/codesnippet/cpp/cmapstringtoob-class_2.cpp)]  
  
##  <a name="gethashtablesize"></a>  CMapStringToOb::GetHashTableSize  
 Bestimmt die aktuelle Anzahl der Elemente in der Hashtabelle.  
  
```  
UINT GetHashTableSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Elemente in der Hashtabelle zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::GetHashTableSize`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**"Uint" GetHashTableSize () const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**"Uint" GetHashTableSize () const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**"Uint" GetHashTableSize () const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**"Uint" GetHashTableSize () const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**"Uint" GetHashTableSize () const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**"Uint" GetHashTableSize () const;**|  
  
##  <a name="getnextassoc"></a>  CMapStringToOb::GetNextAssoc  
 Ruft das kartenelement auf *rNextPosition*, aktualisiert dann *rNextPosition* zum Verweisen auf das nächste Element in der Zuordnung.  
  
```  
void GetNextAssoc(
    POSITION& rNextPosition,  
    CString& rKey,  
    CObject*& rValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *rNextPosition*  
 Gibt einen Verweis auf eine **POSITION** von einem vorherigen zurückgegebene Wert **GetNextAssoc** oder **GetStartPosition** aufrufen.  
  
 *rKey*  
 Gibt an, der zurückgegebene Schlüssel des abgerufenen Elements (Zeichenfolge).  
  
 *rValue*  
 Gibt den zurückgegebenen Wert, der das abgerufene Element (eine **CObject** Zeiger). Finden Sie weitere Informationen zu diesem Parameter unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist besonders hilfreich für die Iteration durch alle Elemente in der Zuordnung. Beachten Sie, dass die Sequenz Position nicht notwendigerweise die Sequenz von Schlüssel-Wert identisch ist.  
  
 Wenn das abgerufene Element das letzte Element in der Zuordnung klicken Sie dann der neue Wert des *rNextPosition* festgelegt ist, um **NULL**.  
  
 Für die *rValue* Parameter, achten Sie darauf, dass Sie Ihre Objekttyp umgewandelt **CObject\*&**, also was erfordert, dass der Compiler, wie im folgenden Beispiel gezeigt:  
  
 [!code-cpp[NVC_MFCCollections#65](../../mfc/codesnippet/cpp/cmapstringtoob-class_3.cpp)]  
  
 Dies gilt nicht für **GetNextAssoc** für Karten, die auf Vorlagen basieren.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind **CMapStringToOb::GetNextAssoc**.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**"void" GetNextAssoc (POSITION &** *rNextPosition* **, "void"\* &**  *rKey* **, "void"\* &**  *rValue* **) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**"void" GetNextAssoc (POSITION &** *rNextPosition* **, "void"\* &**  *rKey* **, WORD &** *rValue* **) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**"void" GetNextAssoc (POSITION &** *rNextPosition* **, CString &** *rKey* **, "void"\* &**  *rValue* **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**"void" GetNextAssoc (POSITION &** *rNextPosition* **, CString &** *rKey* **, CString &** *rValue* **) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**"void" GetNextAssoc (POSITION &** *rNextPosition* **, WORD &** *rKey* **, CObject\* &**  *rValue* **) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**"void" GetNextAssoc (POSITION &** *rNextPosition* **, WORD &** *rKey* **, "void"\* &**  *rValue* **) const;**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) für eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections#66](../../mfc/codesnippet/cpp/cmapstringtoob-class_4.cpp)]  
  
 Die Ergebnisse der dieses Programm sind wie folgt aus:  
  
 `Lisa : a CAge at $4724 11`  
  
 `Marge : a CAge at $47A8 35`  
  
 `Homer : a CAge at $4766 36`  
  
 `Bart : a CAge at $45D4 13`  
  
##  <a name="getsize"></a>  CMapStringToOb::GetSize  
 Gibt die Anzahl der Elemente zurück.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der Zuordnung.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen der Anzahl von Elementen in der Zuordnung.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::GetSize`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetSize( ) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetSize( ) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetSize( ) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetSize( ) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetSize( ) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetSize( ) const;**|  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#67](../../mfc/codesnippet/cpp/cmapstringtoob-class_5.cpp)]  
  
##  <a name="getstartposition"></a>  CMapStringToOb::GetStartPosition  
 Startet eine Iteration Zuordnung wird durch Zurückgeben einer **POSITION** -Wert, der übergeben werden kann eine `GetNextAssoc` aufrufen.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** Wert, der eine Startposition für die Karte; durchlaufen angibt oder **NULL** , wenn die Zuordnung leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Sequenz Iteration ist nicht vorhersagbar; Daher muss der "ersten Element in der Zuordnung" keine andere besonderen Bedeutung.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::GetStartPosition`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**POSITION GetStartPosition( ) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**POSITION GetStartPosition( ) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**POSITION GetStartPosition( ) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**POSITION GetStartPosition( ) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**POSITION GetStartPosition( ) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**POSITION GetStartPosition( ) const;**|  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMapStringToOb::GetNextAssoc](#getnextassoc).  
  
##  <a name="hashkey"></a>  CMapStringToOb::HashKey  
 Berechnet den Hashwert eines angegebenen Schlüssels.  
  
```  
UINT HashKey(LPCTSTR key) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüssel, dessen Hashwert wird berechnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Hashwert des Schlüssels  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::HashKey`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**HashKey "uint" ("void"\***  `key` **) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**HashKey "uint" ("void"\***  `key` **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**"Uint" HashKey (LPCTSTR** `key` **) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**"Uint" HashKey (LPCTSTR** `key` **) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**"Uint" HashKey (WORD** `key` **) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**"Uint" HashKey (WORD** `key` **) const;**|  
  
##  <a name="inithashtable"></a>  CMapStringToOb::InitHashTable  
 Initialisiert die Hashtabelle.  
  
```  
void InitHashTable(
    UINT hashSize,  
    BOOL bAllocNow = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `hashSize`  
 Anzahl von Einträgen in der Hashtabelle.  
  
 `bAllocNow`  
 Wenn **"true"**, ordnet Sie die Hashtabelle, bei der Initialisierung; andernfalls wird die Tabelle zugeordnet, wenn erforderlich.  
  
### <a name="remarks"></a>Hinweise  
 Für optimale Leistung sollte die Hashtabellengröße eine Primzahl. Um Konflikte zu minimieren, sollten die Größe ungefähr 20 Prozent, die größer als das größte erwartete Dataset entsprechen.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::InitHashTable`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**"void" InitHashTable ("uint"** `hashSize` **, BOOL** `bAllocNow` **= "true");**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**"void" InitHashTable ("uint"** `hashSize` **, BOOL** `bAllocNow` **= "true");**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**"void" InitHashTable ("uint"** `hashSize` **, BOOL** `bAllocNow` **= "true");**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**"void" InitHashTable ("uint"** `hashSize` **, BOOL** `bAllocNow` **= "true");**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**"void" InitHashTable ("uint"** `hashSize` **, BOOL** `bAllocNow` **= "true");**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**"void" InitHashTable ("uint"** `hashSize` **, BOOL** `bAllocNow` **= "true");**|  
  
##  <a name="isempty"></a>  CMapStringToOb::IsEmpty  
 Bestimmt, ob die Zuordnung leer ist.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn diese Zuordnung keine Elemente enthält; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [RemoveAll](#removeall).  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind **CMapStringToOb:: IsEmpty**.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL IsEmpty () const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL IsEmpty () const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL IsEmpty () const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL IsEmpty () const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL IsEmpty () const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL IsEmpty () const;**|  
  
##  <a name="lookup"></a>  CMapStringToOb::Lookup  
 Gibt eine `CObject` Zeiger basierend auf einer `CString` Wert.  
  
```  
BOOL Lookup(
    LPCTSTR key,  
    CObject*& rValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Gibt den Schlüssel, der identifiziert das Element gesucht werden soll.  
  
 `rValue`  
 Gibt den zurückgegebenen Wert aus dem nachgeschlagenen-Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Element gefunden wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 `Lookup` verwendet einen Hashalgorithmus, um das kartenelement schnell mit einem Schlüssel zu ermitteln, die genau übereinstimmt ( `CString` Wert).  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::LookUp`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL-Suche ("void"\***  `key` **, "void"\* &**  `rValue` **) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL-Suche ("void"\***  `key` **, WORD &** `rValue` **) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL-Suche (LPCTSTR** `key` **, "void"\* &**  `rValue` **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL-Suche (LPCTSTR** `key` **, CString &** `rValue` **) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL-Suche (WORD** `key` **, CObject\* &**  `rValue` **) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL-Suche (WORD** `key` **, "void"\* &**  `rValue` **) const;**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) für eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections#68](../../mfc/codesnippet/cpp/cmapstringtoob-class_6.cpp)]  
  
##  <a name="lookupkey"></a>  CMapStringToOb::LookupKey  
 Gibt einen Verweis auf den zugeordneten Schlüssel für das angegebene Schlüssel-Wert zurück.  
  
```  
BOOL LookupKey(
    LPCTSTR key,  
    LPCTSTR& rKey) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Gibt den Schlüssel, der identifiziert das Element gesucht werden soll.  
  
 `rKey`  
 Der Verweis auf den zugehörigen Schlüssel.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Schlüssel gefunden wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden einen Verweis auf ein Schlüssel ist unsicher, wenn verwendet, nachdem das zugehörige Element aus der Zuordnung entfernt wurde oder nachdem die Zuordnung zerstört wurde.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind **CMapStringToOb:: LookupKey**.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL LookupKey (LPCTSTR** `key` **, LPCTSTR &** `rKey` **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL LookupKey (LPCTSTR** `key` **, LPCTSTR &** `rKey` **) const;**|  
  
##  <a name="operator_at"></a>  CMapStringToOb::operator]  
 Praktische Ersatz für die `SetAt` Memberfunktion.  
  
```  
CObject*& operator[ ](lpctstr key);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf einen Zeiger auf eine `CObject` Objekt; oder **NULL** , wenn die Zuordnung leer ist oder `key` liegt außerhalb des gültigen Bereichs.  
  
### <a name="remarks"></a>Hinweise  
 Daher kann er nur auf der linken Seite einer zuweisungsanweisung (ein l-Wert) verwendet werden. Wenn kein Map-Element mit dem angegebenen Schlüssel vorhanden ist, wird ein neues Element erstellt.  
  
 Es gibt keine "rechts" (r), die dieser Operator entspricht, da es besteht die Möglichkeit, die ein Schlüssel in der Zuordnung nicht gefunden werden kann. Verwenden der `Lookup` Member-Funktion für den Abruf von Listenelementen.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind **CMapStringToOb::operator []**.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**"void"\*& []-Operator ("void"\***  `key`  **\);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**WORD & -Operator [] ("void"\***  `key`  **\);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**"void"\*& []-Operator (Lpctstr** `key`  **\);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CString & -Operator [] (Lpctstr** `key`  **\);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CObject\*& []-Operator (Word** `key`  **\);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**"void"\*& []-Operator (Word** `key`  **\);**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) für eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections#72](../../mfc/codesnippet/cpp/cmapstringtoob-class_7.cpp)]  
  
 Die Ergebnisse der dieses Programm sind wie folgt aus:  
  
 `Operator [] example: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $4A02 11`  
  
 `[Bart] = a CAge at $497E 13`  
  
##  <a name="removeall"></a>  CMapStringToOb::RemoveAll  
 Entfernt alle Elemente aus dieser Zuordnung und zerstört der `CString` key-Objekte.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Die `CObject` Objekte verweist, die für jeden Schlüssel nicht beschädigt. Die `RemoveAll` Funktion kann Speicherverluste verursachen, wenn Sie nicht, die auf das verwiesen wird sicherstellen `CObject` Objekte zerstört werden.  
  
 Die Funktion funktioniert ordnungsgemäß, wenn die Zuordnung bereits leer ist.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::RemoveAll`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void RemoveAll( );**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void RemoveAll( );**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void RemoveAll( );**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void RemoveAll( );**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void RemoveAll( );**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void RemoveAll( );**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) für eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections#69](../../mfc/codesnippet/cpp/cmapstringtoob-class_8.cpp)]  
  
##  <a name="removekey"></a>  CMapStringToOb::RemoveKey  
 Sucht nach den Eintrag für die Zuordnung, die den bereitgestellten Schlüssel entspricht; Klicken Sie dann, wenn der Schlüssel gefunden wird, entfernt der Eintrag.  
  
```  
BOOL RemoveKey(LPCTSTR key);
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Gibt die Zeichenfolge, die für die Karte Suche verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Eintrag gefunden und erfolgreich entfernt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dies kann Speicherverluste verursachen, wenn die `CObject` Objekt ist nicht an anderer Stelle gelöscht.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::RemoveKey`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL RemoveKey( void\*** `key` **);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL RemoveKey( void\*** `key` **);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL RemoveKey( LPCTSTR** `key` **);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL RemoveKey( LPCTSTR** `key` **);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL RemoveKey (WORD** `key` **);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL RemoveKey (WORD** `key` **);**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) für eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections#70](../../mfc/codesnippet/cpp/cmapstringtoob-class_9.cpp)]  
  
 Die Ergebnisse der dieses Programm sind wie folgt aus:  
  
 `RemoveKey example: A CMapStringToOb with 3 elements`  
  
 `[Marge] = a CAge at $49A0 35`  
  
 `[Homer] = a CAge at $495E 36`  
  
 `[Bart] = a CAge at $4634 13`  
  
##  <a name="setat"></a>  CMapStringToOb::SetAt  
 Das primäre Mittel zum Einfügen eines Elements in einer Zuordnung.  
  
```  
void SetAt(
    LPCTSTR key,  
    CObject* newValue);
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Gibt die Zeichenfolge, die die Schlüssel des neuen Elements ist.  
  
 `newValue`  
 Gibt an, die `CObject` Zeiger, der den Wert des neuen Elements ist.  
  
### <a name="remarks"></a>Hinweise  
 Zunächst wird der Schlüssel gesucht. Wenn der Schlüssel, gefunden wird und klicken Sie dann der entsprechende Wert geändert wird, Andernfalls wird ein neues Element mit Schlüssel-Wert erstellt.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::SetAt`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void SetAt( void\*** `key` **, void\*** `newValue` **);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**"void" SetAt ("void"\***  `key` **, WORD** `newValue` **);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void SetAt( LPCTSTR** `key` **, void\*** `newValue` **);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void SetAt( LPCTSTR** `key` **, LPCTSTR** `newValue` **);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**"void" SetAt (WORD** `key` **, CObject\***  `newValue` **);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**"void" SetAt (WORD** `key` **, "void"\***  `newValue` **);**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) für eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections#71](../../mfc/codesnippet/cpp/cmapstringtoob-class_10.cpp)]  
  
 Die Ergebnisse der dieses Programm sind wie folgt aus:  
  
 `before Lisa's birthday: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $493C 11`  
  
 `[Bart] = a CAge at $4654 13`  
  
 `after Lisa's birthday: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $49C0 12`  
  
 `[Bart] = a CAge at $4654 13`  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr-Klasse](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord-Klasse](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapStringToPtr-Klasse](../../mfc/reference/cmapstringtoptr-class.md)   
 [CMapStringToString-Klasse](../../mfc/reference/cmapstringtostring-class.md)   
 [CMapWordToOb-Klasse](../../mfc/reference/cmapwordtoob-class.md)   
 [CMapWordToPtr-Klasse](../../mfc/reference/cmapwordtoptr-class.md)
