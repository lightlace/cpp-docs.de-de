---
title: CObject-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CObject [MFC], CObject
- CObject [MFC], AssertValid
- CObject [MFC], Dump
- CObject [MFC], GetRuntimeClass
- CObject [MFC], IsKindOf
- CObject [MFC], IsSerializable
- CObject [MFC], Serialize
ms.assetid: 95e9acd3-d9eb-4ac0-b52b-ca4a501a7a3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ccbfc00af51c3327b86386905fb7571f5cbf41fc
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852054"
---
# <a name="cobject-class"></a>CObject-Klasse
Die prinzipale Basisklasse für die Microsoft Foundation Class-Bibliothek.  
  
## <a name="syntax"></a>Syntax  
  
```  
class AFX_NOVTABLE CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObject::CObject](#cobject)|Standardkonstruktor|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObject:: AssertValid](#assertvalid)|Überprüft die Integrität von dieses Objekts.|  
|[CObject::Dump](#dump)|Erzeugt ein Speicherabbild zu Diagnosezwecken dieses Objekts.|  
|[CObject::GetRuntimeClass](#getruntimeclass)|Gibt die `CRuntimeClass` Struktur, Klasse des Objekts entspricht.|  
|[CObject:: IsKindOf](#iskindof)|Testet dieses Objekts Beziehung zu einer angegebenen Klasse.|  
|[CObject::IsSerializable](#isserializable)|Überprüft, ob dieses Objekt serialisiert werden kann.|  
|[CObject:: Serialize](#serialize)|Lädt oder speichert ein Objekt aus dem und in ein Archiv.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObject::operator löschen](#operator_delete)|Spezielle **löschen** Operator.|  
|[Neue CObject::operator](#operator_new)|Spezielle **neue** Operator.|  
  
## <a name="remarks"></a>Hinweise  
 Sie dient als das Stammverzeichnis nicht nur für Klassen der Befehlsbibliothek wie z. B. `CFile` und `CObList`, sondern auch für die Klassen, die Sie schreiben. `CObject` bietet grundlegende Dienste, einschließlich  
  
-   Unterstützung von Serialisierung  
  
-   Laufzeit Klasseninformationen  
  
-   Diagnoseausgaben  
  
-   Kompatibilität mit Auflistungsklassen  
  
 Beachten Sie, dass `CObject` unterstützt keine mehrfachvererbung. Ihren abgeleiteten Klassen sind nur möglich `CObject` Basisklasse und, `CObject` ganz links in der Hierarchie werden muss. Es ist zulässig, allerdings auf Strukturen aufweisen und nicht- `CObject`-abgeleiteten Klassen im rechten mehrfache Vererbung Branches.  
  
 Sie werden bemerken, die Hauptvorteile von `CObject` Ableitung, wenn Sie einige der optionalen Makros in den Deklarationen und Ihre Implementierung verwenden.  
  
 Die Makros, die auf oberster Ebene, [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic) und [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), erlauben Sie die Run-Time-Zugriff auf den Namen der Klasse und ihre Position in der Hierarchie. Dies ermöglicht wiederum die sinnvolle diagnostische Ausgabe.  
  
 Die Makros auf zweiter Ebene [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) und [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial), alle Funktionen der ersten Ebene Makros enthalten, und sie ermöglichen es sich um ein Objekt "an und von"Archiv"."  
  
 Informationen zum Ableiten von Microsoft Foundation Classes und C++-Klassen in der Regel ein, und Verwenden von `CObject`, finden Sie unter [mithilfe von CObject](../../mfc/using-cobject.md) und [Serialisierung](../../mfc/serialization-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="assertvalid"></a>  CObject:: AssertValid  
 Überprüft die Integrität von dieses Objekts.  
  
```  
virtual void AssertValid() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 `AssertValid` führt eine gültigkeitsüberprüfung für dieses Objekt seinen internen Status zu überprüfen. In der Debugversion der Bibliothek `AssertValid` bestätigen können, und daher beendet die Anwendung mit einer Meldung, die auflistet, die Zeilennummer und den Dateinamen, in dem der Assertionsfehler aufgetreten ist.  
  
 Wenn Sie eine eigene Klasse schreiben, sollten Sie Sie überschreiben die `AssertValid` Funktion Diagnosedienste für sich selbst und andere Benutzer der Klasse bereitstellen. Die überschriebene `AssertValid` in der Regel ruft der `AssertValid` Funktion der Basisklasse vor der Überprüfung der Datenmember, die nur für die abgeleitete Klasse.  
  
 Da `AssertValid` ist eine **const** -Funktion, Sie sind nicht berechtigt, den Zustand des Objekts während des Tests zu ändern. Ihre eigene abgeleitete Klasse `AssertValid` Funktionen sollte keine Ausnahmen auslösen, sondern vielmehr sollte bestätigen, ob sie erkennen, dass ungültige Objektdaten.  
  
 Die Definition von "Gültigkeit" hängt die Klasse des Objekts ab. Als Faustregel gilt sollte die Funktion eine "flache überprüfen". durchführen. D.h., wenn ein Objekt Verweise auf andere Objekte enthält, sollte überprüft festzustellen, ob der Zeiger nicht null sind, aber es sollten keine Gültigkeit für die Objekte, die durch die Zeiger bezeichnet testen ausführen.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse zur Verwendung in allen `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]  
  
 Ein weiteres Beispiel finden Sie unter [AfxDoForAllObjects](diagnostic-services.md#afxdoforallobjects).  
  
##  <a name="cobject"></a>  CObject::CObject  
 Diese Funktionen sind die standarddarstellung `CObject` Konstruktoren.  
  
```  
CObject();  
CObject(const CObject& objectSrc);
```  
  
### <a name="parameters"></a>Parameter  
 *objectSrc*  
 Ein Verweis auf einen anderen `CObject`  
  
### <a name="remarks"></a>Hinweise  
 Die Standardversion wird automatisch durch den Konstruktor der abgeleiteten Klasse aufgerufen.  
  
 Wenn Ihre Klasse serialisierbar ist (es enthält die IMPLEMENT_SERIAL-Makro), dann müssen Sie einen Standardkonstruktor (ein Konstruktor ohne Argumente) in Ihrer Klassendeklaration verfügen. Wenn Sie nicht über einen Standardkonstruktor benötigen, deklarieren Sie eines privaten oder geschützten Sie Konstruktor von "empty". Weitere Informationen finden Sie unter [mithilfe von CObject](../../mfc/using-cobject.md).  
  
 Der standard C++ Standard-Copy-Konstruktor wird eine Kopie der Member für Member. Das Vorhandensein des privaten `CObject` Kopierkonstruktor garantiert eine Fehlermeldung des Compilers an, wenn der Kopierkonstruktor der Klasse erforderlich, aber nicht verfügbar ist. Sie müssen daher einen Kopierkonstruktor angeben, wenn Ihre Klasse diese Funktion erfordert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse zur Verwendung in der `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]  
  
##  <a name="dump"></a>  CObject::Dump  
 Gibt den Inhalt des Objekts zu einem [CDumpContext](../../mfc/reference/cdumpcontext-class.md) Objekt.  
  
```  
virtual void Dump(CDumpContext& dc) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *dc*  
 Speicherabbild zu Diagnosezwecken Kontext zum Abrufen, in der Regel `afxDump`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie eine eigene Klasse schreiben, sollten Sie Sie überschreiben die `Dump` Funktion Diagnosedienste für sich selbst und andere Benutzer der Klasse bereitstellen. Die überschriebene `Dump` in der Regel ruft der `Dump` Funktion der Basisklasse vor dem Drucken der Datenmember, die nur für die abgeleitete Klasse. `CObject::Dump` Gibt den Namen der Klasse, wenn Ihre Klasse verwendet die `IMPLEMENT_DYNAMIC` oder IMPLEMENT_SERIAL-Makro.  
  
> [!NOTE]
>  Ihre `Dump` Funktion sollte ein Zeilenumbruchzeichen am Ende die Ausgabe nicht gedruckt.  
  
 `Dump` Aufrufe sind sinnvoll, nur in der Debugversion der Microsoft Foundation Class-Bibliothek. Sie sollten Klammern Anrufe, Deklarationen und Implementierungen mit **#ifdef _DEBUG** /  `#endif` Anweisungen für die bedingte Kompilierung.  
  
 Da `Dump` ist eine **const** -Funktion, Sie sind nicht berechtigt, den Zustand des Objekts während der Dump zu ändern.  
  
 Die [CDumpContext einfügen (<<) Operator](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt) Aufrufe `Dump` bei einem `CObject` Zeiger eingefügt wird.  
  
 `Dump` lässt nur "azyklische" Dump-Sicherungen von Objekten. Sie können eine Liste von Objekten, Sichern z. B. aber wenn eines der Objekte auf die Liste selbst ist, Sie werden schließlich zu einem Stapelüberlauf.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse zur Verwendung in allen `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]  
  
##  <a name="getruntimeclass"></a>  CObject::GetRuntimeClass  
 Gibt die `CRuntimeClass` Struktur, Klasse des Objekts entspricht.  
  
```  
virtual CRuntimeClass* GetRuntimeClass() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Struktur, die für diese Objektklasse; nie **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Es gibt ein `CRuntimeClass` Struktur für die einzelnen `CObject`-abgeleitete Klasse. Die Strukturmember lauten wie folgt aus:  
  
- **LPCSTR M_lpszClassName** eine Null-terminierte Zeichenfolge, die den Namen der ASCII-Klasse enthält.  
  
- **Int M_nObjectSize** die Größe des Objekts in Bytes. Wenn das Objekt, zeigen Sie auf zugewiesenen Speicher Datenmember verfügt, ist die Größe der, dass der Speicher nicht enthalten.  
  
- **UINT M_wSchema** die Schema-Anzahl (-1 für nicht serialisierbare Klassen). Finden Sie unter den [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) Makro eine Beschreibung der Schema-Anzahl.  
  
- **CObject\* (Pascal-SCHREIBWEISE\* CRuntimeClass) ()** ein Funktionszeiger auf den Standardkonstruktor, der ein Objekt der Klasse erstellt (gültig nur dann, wenn die Klasse dynamische Erstellung unterstützt; andernfalls **NULL** ).  
  
- **CRuntimeClass\* (Pascal-SCHREIBWEISE\* M_pfn_GetBaseClass) ()** Wenn Ihre Anwendung auf die AFXDLL-Version von MFC dynamisch verknüpft ist, ein Zeiger auf eine Funktion, die gibt die `CRuntimeClass` Struktur der Basisklasse.  
  
- **CRuntimeClass\* M_pBaseClass** , wenn Ihre Anwendung statisch mit MFC, ein Zeiger auf verknüpft ist die `CRuntimeClass` Struktur der Basisklasse.  
  
 Diese Funktion erfordert die Verwendung der [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate), oder [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) Makro in der klassenimplementierung. Andernfalls erhalten Sie falsche Ergebnisse.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse zur Verwendung in allen `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]  
  
##  <a name="iskindof"></a>  CObject:: IsKindOf  
 Testet dieses Objekts Beziehung zu einer angegebenen Klasse.  
  
```  
BOOL IsKindOf(const CRuntimeClass* pClass) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *pClass*  
 Ein Zeiger auf eine [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Struktur zugeordnet ist Ihre `CObject`-abgeleitete Klasse.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn das Objekt der Klasse entspricht; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion prüft *pClass* um festzustellen, ob die (1) Es handelt sich um ein Objekt der angegebenen Klasse oder (2) Es handelt sich um ein Objekt einer Klasse, die von der angegebenen Klasse abgeleitet. Diese Funktion funktioniert nur für Klassen, die mit der [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic), [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate), oder [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) Makro.  
  
 Verwenden Sie diese Funktion nicht häufig auf, da es die C++-Polymorphie-Funktion verfehlt. Verwenden Sie stattdessen virtuelle Funktionen.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse zur Verwendung in allen `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]  
  
##  <a name="isserializable"></a>  CObject::IsSerializable  
 Testet, ob dieses Objekt für die Serialisierung geeignet ist.  
  
```  
BOOL IsSerializable() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn dieses Objekt serialisiert werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Für eine Klasse serialisierbar sein, darf der Deklaration der [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) -Makro, und die Implementierung darf die [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) Makro.  
  
> [!NOTE]
>  Überschreiben Sie diese Funktion nicht.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse zur Verwendung in allen `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample#12](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]  
  
##  <a name="operator_delete"></a>  CObject::operator löschen  
 Für die Releaseversion der Bibliothek Operator **löschen** gibt den Arbeitsspeicher frei von Operator **neue**.  
  
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
 In der Debugversion Operator **löschen** ein Allocation-monitoring-Schema entwickelt, um das Erkennen von Speicherverlusten beteiligt.  
  
 Wenn Sie die Codezeile verwenden  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]  
  
 vor allen Ihren Implementierungen in ein. CPP-Datei, klicken Sie dann die dritte Version von **löschen** verwendet werden, speichern die Anzahl von Dateinamen und Zeilennummern in belegten Blocks für die spätere berichterstellung. Sie müssen keine Gedanken um die zusätzlichen Parameter angeben; ein Makro übernimmt, die für Sie.  
  
 Auch wenn Sie DEBUG_NEW im Debugmodus nicht verwenden, erhalten Sie trotzdem Erkennung von Speicherverlusten, jedoch ohne die Quelldatei Zeilennummern berichterstellung oben beschrieben.  
  
 Wenn Sie Operatoren überschreiben **neue** und **löschen**, Sie in Anspruch genommenen diese Diagnose-Funktion.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse zur Verwendung in der `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample#15](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]  
  
##  <a name="operator_new"></a>  Neue CObject::operator  
 Für die Releaseversion der Bibliothek Operator **neue** führt eine optimale speicherbelegung auf ähnliche Weise `malloc`.  
  
```  
void* PASCAL operator new(size_t nSize);  
void* PASCAL operator new(size_t, void* p);

 
void* PASCAL operator new(
    size_t nSize,  
    LPCSTR lpszFileName,  
    int nLine);
```  
  
### <a name="remarks"></a>Hinweise  
 In der Debugversion Operator **neue** ein Allocation-monitoring-Schema entwickelt, um das Erkennen von Speicherverlusten beteiligt.  
  
 Wenn Sie die Codezeile verwenden  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]  
  
 vor allen Ihren Implementierungen in ein. CPP-Datei, klicken Sie dann die zweite Version der **neue** verwendet werden, speichern die Anzahl von Dateinamen und Zeilennummern in belegten Blocks für die spätere berichterstellung. Sie müssen keine Gedanken um die zusätzlichen Parameter angeben; ein Makro übernimmt, die für Sie.  
  
 Auch wenn Sie DEBUG_NEW im Debugmodus nicht verwenden, erhalten Sie trotzdem Erkennung von Speicherverlusten, jedoch ohne die Quelldatei Zeilennummern berichterstellung oben beschrieben.  
  
> [!NOTE]
>  Wenn Sie diesen Operator überschreiben, müssen Sie auch überschreiben **löschen**. Verwenden Sie nicht die Standardbibliothek `_new_handler` Funktion.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse zur Verwendung in der `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]  
  
##  <a name="serialize"></a>  CObject:: Serialize  
 Liest oder schreibt dieses Objekt aus einem oder in ein Archiv.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 *ar*  
 Ein `CArchive` zu zu oder von zu serialisierenden Objekts.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen überschreiben `Serialize` für jede Klasse, die serialisiert werden soll. Die überschriebene `Serialize` müssen rufen Sie zuerst die `Serialize` Funktion der Basisklasse.  
  
 Sie müssen auch verwenden die [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) Makro in der Klassendeklaration, und Sie verwenden, muss die [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) Makro in der Implementierung.  
  
 Verwendung [CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) oder [CArchive::IsStoring](../../mfc/reference/carchive-class.md#isstoring) zu bestimmen, ob das Archiv laden oder speichern.  
  
 `Serialize` wird aufgerufen, indem [CArchive::ReadObject](../../mfc/reference/carchive-class.md#readobject) und [CArchive::WriteObject](../../mfc/reference/carchive-class.md#writeobject). Diese Funktionen zugeordnet sind die `CArchive` Operator zum Einfügen ( **< \<**) und Extraktionsoperator ( **>>**).  
  
 Beispiele zur Serialisierung finden Sie im Artikel [Serialisierung: Serialisieren eines Objekts](../../mfc/serialization-serializing-an-object.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse zur Verwendung in allen `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



