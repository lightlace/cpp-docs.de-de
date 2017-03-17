---
title: CObject-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CObject
- AFX/CObject
- AFX/CObject::CObject
- AFX/CObject::AssertValid
- AFX/CObject::Dump
- AFX/CObject::GetRuntimeClass
- AFX/CObject::IsKindOf
- AFX/CObject::IsSerializable
- AFX/CObject::Serialize
dev_langs:
- C++
helpviewer_keywords:
- base classes, MFC objects
- objects [C++], base class for MFC
- object classes
- CObject class
ms.assetid: 95e9acd3-d9eb-4ac0-b52b-ca4a501a7a3a
caps.latest.revision: 22
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d411b9da8618eaac57045a1db05251517422976a
ms.lasthandoff: 02/24/2017

---
# <a name="cobject-class"></a>CObject-Klasse
Die prinzipale Basisklasse für die Microsoft Foundation Class-Bibliothek.  
  
## <a name="syntax"></a>Syntax  
  
```  
class AFX_NOVTABLE CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObject::CObject](#cobject)|Standardkonstruktor|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObject:: AssertValid](#assertvalid)|Überprüft die Integrität des Objekts.|  
|[CObject::Dump](#dump)|Erzeugt einen diagnostic Dump dieses Objekts.|  
|[CObject::GetRuntimeClass](#getruntimeclass)|Gibt die `CRuntimeClass` Struktur, Klasse des Objekts entspricht.|  
|[CObject:: IsKindOf](#iskindof)|Dieses Objekt Beziehung zu einer bestimmten Klasse wird überprüft.|  
|[CObject::IsSerializable](#isserializable)|Überprüft, ob dieses Objekt serialisiert werden kann.|  
|[CObject:: Serialize](#serialize)|Lädt oder speichert ein Objekt aus dem und in ein Archiv.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObject::operator löschen](#operator_delete)|Besondere **löschen** Operator.|  
|[Neue CObject::operator](#operator_new)|Besondere **neue** Operator.|  
  
## <a name="remarks"></a>Hinweise  
 Sie dient als Stamm nicht nur für Klassen wie z. B. `CFile` und `CObList`, sondern auch für die Klassen, die Sie schreiben. `CObject`Stellt grundlegende Dienste, einschließlich  
  
-   Unterstützung von Serialisierung  
  
-   Laufzeit Klasseninformationen  
  
-   Diagnoseausgaben  
  
-   Kompatibilität mit Auflistungsklassen  
  
 Beachten Sie, dass `CObject` mehrfache Vererbung nicht unterstützt. Die abgeleiteten Klassen sind nur möglich `CObject` Basisklasse und dass `CObject` muss in der Hierarchie ganz links. Es ist zulässig, jedoch Strukturen aufweisen und nicht- `CObject`-abgeleiteten Klassen im rechten mehrfache Vererbung Verzweigungen.  
  
 Erkennen Sie wichtige Vorteile von `CObject` Ableitung, wenn Sie einige der optionalen Makros in den Deklarationen und Ihre Implementierung verwenden.  
  
 Die Makros, die auf der obersten Ebene, [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic) und [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), zur Laufzeit Zugriff auf den Klassennamen und seine Position in der Hierarchie. Dies ermöglicht wiederum die sinnvolle diagnostische Ausgabe.  
  
 Die Makros auf zweiter Ebene [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) und [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial), alle Funktionen der ersten Ebene Makros enthalten, und sie ein Objekt, das ", und aus einem"Archiv"serialisiert" aktivieren  
  
 Informationen zum Ableiten Microsoft Foundation Classes und C++-Klassen im Allgemeinen sowie `CObject`, finden Sie unter [mithilfe von CObject](../../mfc/using-cobject.md) und [Serialisierung](../../mfc/serialization-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="assertvalid"></a>CObject:: AssertValid  
 Überprüft die Integrität des Objekts.  
  
```  
virtual void AssertValid() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 `AssertValid`führt eine gültigkeitsüberprüfung für dieses Objekt durch seinen internen Status zu überprüfen. In der Debugversion der Bibliothek `AssertValid` bestätigen und somit die Anwendung mit einer Meldung, die auflistet, die Zeilennummer und den Dateinamen, in denen Fehler bei die Assertion beenden kann.  
  
 Wenn Sie eine eigene Klasse schreiben, sollten Sie überschreiben die `AssertValid` der Funktion Diagnosedienste für sich selbst und anderen Benutzern Ihrer Klasse. Die überschriebene `AssertValid` in der Regel ruft die `AssertValid` Funktion der Basisklasse vor der Prüfung der Datenmember, die nur in der abgeleiteten Klasse.  
  
 Da `AssertValid` ist ein **const** -Funktion, Sie sind nicht berechtigt, den Objektstatus während des Tests zu ändern. Ihre eigene abgeleitete Klasse `AssertValid` Funktionen sollte keine Ausnahmen auslösen, sondern vielmehr sollte bestätigen, ob sie ungültige Daten erkannt.  
  
 Die Definition von "Gültigkeit" hängt die Klasse des Objekts ab. In der Regel sollte die Funktion ausführen "flache überprüfen". Wenn ein Objekt Verweise auf andere Objekte enthält, sollte sie also darauf, ob der Zeiger nicht null sind, er jedoch nicht ausführen Gültigkeit Tests auf die Objekte, die durch die Zeiger bezeichnet überprüfen.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse zur Verwendung in allen `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample&#7;](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]  
  
 Ein weiteres Beispiel finden Sie unter [AfxDoForAllObjects](diagnostic-services.md#afxdoforallobjects).  
  
##  <a name="cobject"></a>CObject::CObject  
 Diese Funktionen sind dem Standard `CObject` Konstruktoren.  
  
```  
CObject();  
CObject(const CObject& objectSrc);
```  
  
### <a name="parameters"></a>Parameter  
 *objectSrc*  
 Ein Verweis auf ein anderes`CObject`  
  
### <a name="remarks"></a>Hinweise  
 Die Standard-Version wird automatisch durch den Konstruktor der abgeleiteten Klasse aufgerufen.  
  
 Wenn Ihre Klasse serialisierbar ist (es enthält die `IMPLEMENT_SERIAL` Makro), müssen Sie einen Standardkonstruktor (einen Konstruktor ohne Argumente) in der Klassendeklaration enthalten. Wenn Sie nicht über einen Standardkonstruktor benötigen, deklarieren Sie einen privaten oder geschützten Sie Konstruktor "empty". Weitere Informationen finden Sie unter [mithilfe von CObject](../../mfc/using-cobject.md).  
  
 Der standard C++-Klasse Standardkopierkonstruktor ist eine Kopie von Mitgliedern. Das Vorhandensein des privaten `CObject` Kopierkonstruktor garantiert eine Fehlermeldung des Compilers, wenn der Kopierkonstruktor der Klasse erforderlich, aber nicht verfügbar ist. Sie müssen daher einen Kopierkonstruktor angeben, wenn Ihre Klasse diese Funktion erfordert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse zur Verwendung in der `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample&#8;](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]  
  
##  <a name="dump"></a>CObject::Dump  
 Zeigt den Inhalt des Objekts ein [CDumpContext](../../mfc/reference/cdumpcontext-class.md) Objekt.  
  
```  
virtual void Dump(CDumpContext& dc) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `dc`  
 Die Diagnose Dumpkontext zum ausgeben, in der Regel `afxDump`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie eine eigene Klasse schreiben, sollten Sie überschreiben die `Dump` der Funktion Diagnosedienste für sich selbst und anderen Benutzern Ihrer Klasse. Die überschriebene `Dump` in der Regel ruft die `Dump` Funktion der Basisklasse vor dem Drucken Datenmember, die nur in der abgeleiteten Klasse. `CObject::Dump`Gibt den Klassennamen, wenn Ihre Klasse verwendet die `IMPLEMENT_DYNAMIC` oder `IMPLEMENT_SERIAL` Makro.  
  
> [!NOTE]
>  Ihre `Dump` Funktion sollte ein Zeilenumbruchzeichen am Ende der Ausgabe nicht gedruckt.  
  
 `Dump`Aufrufe sind sinnvoll, nur in der Debugversion der Microsoft Foundation Class-Bibliothek. Sie sollten Klammern Anrufe, Funktionsdeklarationen und Implementieren von Funktionen mit **#ifdef _DEBUG** /  `#endif` Anweisungen für die bedingte Kompilierung.  
  
 Da `Dump` ist ein **const** -Funktion, Sie sind nicht berechtigt, den Zustand des Objekts während der Dump zu ändern.  
  
 Die [CDumpContext einfügen (<)> </)> ](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt) Aufrufe `Dump` bei einem `CObject` Zeiger eingefügt wird.  
  
 `Dump`lässt nur "azyklische" Einbringung von Objekten. Von Abbildern haben Sie eine Liste von Objekten, z. B. aber ist eines der Objekte die Liste selbst, Sie werden schließlich zu einem Stapelüberlauf.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse zur Verwendung in allen `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample&#9;](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]  
  
##  <a name="getruntimeclass"></a>CObject::GetRuntimeClass  
 Gibt die `CRuntimeClass` Struktur, Klasse des Objekts entspricht.  
  
```  
virtual CRuntimeClass* GetRuntimeClass() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) die Struktur für diese Objektklasse; nie **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Es gibt ein `CRuntimeClass` Struktur für jede `CObject`-abgeleiteten Klasse. Die Strukturmember lauten wie folgt:  
  
- **LPCSTR M_lpszClassName** eine Null-terminierte Zeichenfolge mit dem Namen der ASCII-Klasse.  
  
- **Int M_nObjectSize** die Größe des Objekts in Bytes. Wenn das Objekt, zeigen Sie auf den belegten Speicher Datenmember verfügt, ist die Größe dieses Speichers nicht enthalten.  
  
- **UINT M_wSchema** die Schema-Anzahl (– 1 für nicht serialisierbare Klassen). Finden Sie unter der [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) Makro für eine Beschreibung des Schema-Anzahl.  
  
- **CObject\* (PASCAL\* CRuntimeClass) ()** ein Funktionszeiger, der den Standardkonstruktor, der ein Objekt der Klasse erstellt (gültig nur, wenn die Klasse dynamische Erstellung unterstützt; andernfalls **NULL**).  
  
- **CRuntimeClass\* (PASCAL\* M_pfn_GetBaseClass) ()** , wenn Ihre Anwendung dynamisch mit der AFXDLL-Version von MFC verknüpft ist, ein Zeiger auf eine Funktion, die gibt die `CRuntimeClass` Struktur der Basisklasse.  
  
- **CRuntimeClass\* M_pBaseClass** , wenn Ihre Anwendung statisch mit MFC, ein Zeiger auf Verknüpfte der `CRuntimeClass` Struktur der Basisklasse.  
  
 Diese Funktion erfordert die Verwendung der [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate), oder [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) Makro in die Implementierung der Klasse. Sie erhalten falsche Ergebnisse andernfalls.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse zur Verwendung in allen `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample&#10;](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]  
  
##  <a name="iskindof"></a>CObject:: IsKindOf  
 Dieses Objekt Beziehung zu einer bestimmten Klasse wird überprüft.  
  
```  
BOOL IsKindOf(const CRuntimeClass* pClass) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pClass`  
 Ein Zeiger auf eine [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Struktur zugeordnet ist die `CObject`-abgeleiteten Klasse.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn das Objekt der Klasse entspricht; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion prüft `pClass` (1) ist ein Objekt der angegebenen Klasse oder (2) ist ein Objekt einer Klasse, die von der angegebenen Klasse abgeleitet. Diese Funktion ist nur für Klassen, die mit der [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic), [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate), oder [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) Makro.  
  
 Verwenden Sie diese Funktion nicht häufig auf, da es der Polymorphie-Funktion von C++ unterlaufen kann. Verwenden Sie stattdessen virtuelle Funktionen.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse zur Verwendung in allen `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample&#11;](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]  
  
##  <a name="isserializable"></a>CObject::IsSerializable  
 Testet, ob dieses Objekt für die Serialisierung berechtigt ist.  
  
```  
BOOL IsSerializable() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn dieses Objekt serialisiert werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Für eine Klasse, die serialisierbar sein, dessen Deklaration darf die [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) -Makro, und die Implementierung darf die [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) Makro.  
  
> [!NOTE]
>  Überschreiben Sie diese Funktion nicht.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse zur Verwendung in allen `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample&#12;](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]  
  
##  <a name="operator_delete"></a>CObject::operator löschen  
 Für die endgültige Produktversion von der Bibliothek Operator **löschen** gibt den Arbeitsspeicher frei von Operator **neue**.  
  
```  
void PASCAL operator delete(void* p);

 
void PASCAL operator delete(
    void* p,
    void* pPlace);

 
void PASCAL operator delete(
    void* p,  
    LPCSTR lpszFileName,  
    int nLine);
```  
  
### <a name="remarks"></a>Hinweise  
 In der Debugversion Operator **löschen** Beteiligung an der eine Zuordnung Überwachung Schema entwickelt, um Speicherverluste zu ermitteln.  
  
 Wenn Sie die Codezeile verwenden  
  
 [!code-cpp[NVC_MFCCObjectSample&14;](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]  
  
 vor der Implementierung in einer. CPP-Datei, klicken Sie dann die dritte Version von **löschen** verwendet werden, der Dateiname und Zeilennummer angegeben in den reservierten Block Fehlerbericht speichern. Sie müssen keine Gedanken, geben Sie die zusätzlichen Parameter; ein Makro übernimmt, die für Sie.  
  
 Auch wenn Sie nicht verwenden `DEBUG_NEW` im Debugmodus befindet, erhalten Sie weiterhin Erkennung von Speicherverlusten, jedoch ohne die Quelldatei Zeilennummer reporting oben beschrieben.  
  
 Wenn Sie Operatoren überschreiben **neue** und **löschen**, Sie dies diagnostische verfallen.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse zur Verwendung in der `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample&#15;](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]  
  
##  <a name="operator_new"></a>Neue CObject::operator  
 Für die endgültige Produktversion von der Bibliothek Operator **neue** führt eine optimale speicherbelegung in ähnlicher Weise `malloc`.  
  
```  
void* PASCAL operator new(size_t nSize);  
void* PASCAL operator new(size_t, void* p);

 
void* PASCAL operator new(
    size_t nSize,  
    LPCSTR lpszFileName,  
    int nLine);
```  
  
### <a name="remarks"></a>Hinweise  
 In der Debugversion Operator **neue** Beteiligung an der eine Zuordnung Überwachung Schema entwickelt, um Speicherverluste zu ermitteln.  
  
 Wenn Sie die Codezeile verwenden  
  
 [!code-cpp[NVC_MFCCObjectSample&14;](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]  
  
 vor der Implementierung in einer. CPP-Datei, klicken Sie dann die zweite Version der **neue** verwendet werden, der Dateiname und Zeilennummer angegeben in den reservierten Block Fehlerbericht speichern. Sie müssen keine Gedanken, geben Sie die zusätzlichen Parameter; ein Makro übernimmt, die für Sie.  
  
 Auch wenn Sie nicht verwenden `DEBUG_NEW` im Debugmodus befindet, erhalten Sie weiterhin Erkennung von Speicherverlusten, jedoch ohne die Quelldatei Zeilennummer reporting oben beschrieben.  
  
> [!NOTE]
>  Wenn Sie diesen Operator überschreiben, müssen Sie auch überschreiben **löschen**. Verwenden Sie nicht die Standardbibliothek **_new_handler** Funktion.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse zur Verwendung in der `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample Nr.&16;](../../mfc/codesnippet/cpp/cobject-class_9.h)]  
  
##  <a name="serialize"></a>CObject:: Serialize  
 Liest oder schreibt dieses Objekt aus einem oder in ein Archiv.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 `ar`  
 Ein `CArchive` Objekt serialisieren in oder aus.  
  
### <a name="remarks"></a>Hinweise  
 Sie überschreiben müssen `Serialize` für jede Klasse, die Sie serialisieren möchten. Die überschriebene `Serialize` müssen zuerst aufrufen, die `Serialize` Funktion der Basisklasse.  
  
 Sie müssen auch verwenden die [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) Makro in der Klassendeklaration, und Sie verwenden muss die [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) Makro in der Implementierung.  
  
 Verwendung [CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) oder [CArchive::IsStoring](../../mfc/reference/carchive-class.md#isstoring) zu bestimmen, ob das Archiv laden oder speichern.  
  
 `Serialize`wird aufgerufen, indem [CArchive::ReadObject](../../mfc/reference/carchive-class.md#readobject) und [CArchive::WriteObject](../../mfc/reference/carchive-class.md#writeobject). Diese Funktionen im Zusammenhang mit der `CArchive` Operator zum Einfügen ( ** < \< **) und Extraktionsoperator ( ** >> **).  
  
 Beispiele zur Serialisierung finden Sie im Artikel [Serialisierung: Serialisieren eines Objekts](../../mfc/serialization-serializing-an-object.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse zur Verwendung in allen `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample&#13;](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




