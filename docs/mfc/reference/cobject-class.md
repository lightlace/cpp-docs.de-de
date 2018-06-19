---
title: CObject-Klasse | Microsoft Docs
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
ms.openlocfilehash: 38c27d2fa0e04770bae69901e1164da84c2186ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377239"
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
|[CObject:: AssertValid](#assertvalid)|Überprüft die Integrität des Objekts.|  
|[CObject::Dump](#dump)|Erzeugt einen Diagnose Dump dieses Objekts an.|  
|[CObject::GetRuntimeClass](#getruntimeclass)|Gibt die `CRuntimeClass` Struktur, Klasse des Objekts entspricht.|  
|[CObject:: IsKindOf](#iskindof)|Testet, dieses Objekt Beziehung zu einer angegebenen Klasse.|  
|[CObject::IsSerializable](#isserializable)|Überprüft, ob dieses Objekt serialisiert werden kann.|  
|[Einfügeoperatoren](#serialize)|Lädt oder speichert ein Objekt aus/in ein Archiv.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObject::operator löschen](#operator_delete)|Spezielle **löschen** Operator.|  
|[Neue CObject::operator](#operator_new)|Spezielle **neue** Operator.|  
  
## <a name="remarks"></a>Hinweise  
 Es dient als das Stammverzeichnis nicht nur Bibliotheksklassen wie z. B. `CFile` und `CObList`, sondern auch für die Klassen, die Sie schreiben. `CObject` Stellt grundlegende Dienste, einschließlich  
  
-   Unterstützung von Serialisierung  
  
-   Laufzeit Klasseninformationen  
  
-   Diagnoseausgabe Objekt  
  
-   Kompatibilität mit Auflistungsklassen  
  
 Beachten Sie, dass `CObject` unterstützt keine mehrfachvererbung. Die abgeleiteten Klassen sind nur möglich `CObject` Basisklasse und dass `CObject` muss die am weitesten links in der Hierarchie. Es ist zulässig, allerdings Strukturen aufweisen und nicht- `CObject`-abgeleiteten Klassen im rechten mehrfache Vererbung Verzweigungen.  
  
 Sie werden wichtigsten Vorzüge von `CObject` Ableitung, wenn Sie einige der optionalen Makros in Ihrer klassenimplementierung und Deklarationen verwenden.  
  
 Die Makros auf oberster Ebene [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic) und [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), lassen Sie zur Laufzeit den Zugriff auf den Klassennamen und seine Position in der Hierarchie. Dies ermöglicht wiederum sinnvolle diagnostische sichern.  
  
 Die Makros auf zweiter Ebene [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) und [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial), umfassen alle Funktionen der ersten Ebene Makros und bieten ein Objekt, "verschiedene andere und aus einem"Archiv"serialisiert werden soll"  
  
 Informationen zum Ableiten von Microsoft Foundation Classes und C++-Klassen im Allgemeinen und Verwenden von `CObject`, finden Sie unter [Verwenden von CObject](../../mfc/using-cobject.md) und [Serialisierung](../../mfc/serialization-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="assertvalid"></a>  CObject:: AssertValid  
 Überprüft die Integrität des Objekts.  
  
```  
virtual void AssertValid() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 `AssertValid` führt eine gültigkeitsüberprüfung für dieses Objekt durch den internen Zustand überprüfen. In der Debugversion der Bibliothek `AssertValid` bestätigen kann, und daher beendet das Programm mit einer Meldung, die die Quellzeilennummer und den auflistet, in dem der Assertionsfehler aufgetreten ist.  
  
 Wenn Sie eine eigene Klasse schreiben, sollten Sie überschreiben die `AssertValid` Funktion zur Diagnose selbst und anderen Benutzern Ihrer Klasse Dienstleistungen. Die überschriebene `AssertValid` in der Regel ruft der `AssertValid` Funktion der Basisklasse vor der Überprüfung von Datenelementen, die für die abgeleitete Klasse eindeutig.  
  
 Da `AssertValid` ist ein **const** -Funktion, Sie sind nicht berechtigt, den Zustand des Objekts während der Tests zu ändern. Eine eigene abgeleitete Klasse `AssertValid` Funktionen sollte keine Ausnahmen auslösen, sondern stattdessen sollte bestätigen, ob sie ungültige Daten erkannt.  
  
 Die Definition von "Gültigkeit" hängt von der Object-Klasse. In der Regel sollte die Funktion "flache Check". durchführen. D. h. wenn ein Objekt, Zeiger auf andere Objekte enthält, sollte es überprüfen, ob der Zeiger nicht null sind, aber es sollten keine Tests für die Objekte, die der Zeiger verweist auf Gültigkeit ausführen.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) für eine Liste der `CAge` Klasse zur Verwendung in allen `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]  
  
 Ein weiteres Beispiel finden Sie unter [AfxDoForAllObjects](diagnostic-services.md#afxdoforallobjects).  
  
##  <a name="cobject"></a>  CObject::CObject  
 Diese Funktionen befinden sich die Standard `CObject` Konstruktoren.  
  
```  
CObject();  
CObject(const CObject& objectSrc);
```  
  
### <a name="parameters"></a>Parameter  
 *objectSrc*  
 Ein Verweis auf eine andere `CObject`  
  
### <a name="remarks"></a>Hinweise  
 Die Standardversion wird vom Konstruktor einer abgeleiteten Klasse automatisch aufgerufen.  
  
 Wenn Ihre Klasse serialisierbar ist (er beinhaltet die `IMPLEMENT_SERIAL` Makro), dann müssen Sie einen Standardkonstruktor (einen Konstruktor ohne Argumente) in der Klassendeklaration verfügen. Wenn Sie nicht über einen Standardkonstruktor benötigen, deklarieren Sie eines privaten oder geschützten Sie Konstruktor "empty". Weitere Informationen finden Sie unter [Verwenden von CObject](../../mfc/using-cobject.md).  
  
 Der standard C++ Standard-Copy-Konstruktor wird eine Kopie von Mitgliedern. Das Vorhandensein des privaten `CObject` Kopierkonstruktor gewährleistet eine Fehlermeldung des Compilers, wenn es sich bei der Kopierkonstruktor der Klasse erforderlich, aber nicht verfügbar ist. Sie müssen daher einen Kopierkonstruktor angeben, wenn Ihre Klasse diese Funktion erfordert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) für eine Liste der `CAge` Klasse zur Verwendung in der `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]  
  
##  <a name="dump"></a>  CObject::Dump  
 Gibt den Inhalt des Objekts ein [CDumpContext](../../mfc/reference/cdumpcontext-class.md) Objekt.  
  
```  
virtual void Dump(CDumpContext& dc) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `dc`  
 Die Diagnose Dumpkontext für Sicherung, in der Regel `afxDump`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie eine eigene Klasse schreiben, sollten Sie überschreiben die `Dump` Funktion zur Diagnose selbst und anderen Benutzern Ihrer Klasse Dienstleistungen. Die überschriebene `Dump` in der Regel ruft der `Dump` Funktion der Basisklasse vor dem Drucken Datenmember, die für die abgeleitete Klasse eindeutig. `CObject::Dump` Gibt den Klassennamen abrufen, wenn Ihre Klasse verwendet die `IMPLEMENT_DYNAMIC` oder `IMPLEMENT_SERIAL` Makro.  
  
> [!NOTE]
>  Ihre `Dump` Funktion sollte ein Zeilenumbruchzeichen am Ende der Ausgabe nicht gedruckt.  
  
 `Dump` Aufrufe sinnvoll nur in der Debugversion der Microsoft Foundation Class-Bibliothek. Sie sollten Klammer Anrufe, Funktionsdeklarationen und funktionsimplementierungen mit **#ifdef _DEBUG** /  `#endif` Anweisungen für die bedingte Kompilierung.  
  
 Da `Dump` ist ein **const** -Funktion, Sie sind nicht berechtigt, den Objektstatus während das Speicherabbild zu ändern.  
  
 Die [CDumpContext einfügen (<<) Operator](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt) Aufrufe `Dump` bei einem `CObject` Zeiger eingefügt wird.  
  
 `Dump` lässt nur "azyklisch" Dump-Sicherungen von Objekten. Abbildern haben Sie eine Liste von Objekten, z. B. aber wenn eines der Objekte der Liste selbst ist, Sie werden schließlich zu einem Stapelüberlauf.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) für eine Liste der `CAge` Klasse zur Verwendung in allen `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]  
  
##  <a name="getruntimeclass"></a>  CObject::GetRuntimeClass  
 Gibt die `CRuntimeClass` Struktur, Klasse des Objekts entspricht.  
  
```  
virtual CRuntimeClass* GetRuntimeClass() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Struktur, die für diese Objektklasse; nie **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Es ist eine `CRuntimeClass` Struktur für jedes `CObject`-abgeleitete Klasse. Die Strukturmember lauten wie folgt:  
  
- **LPCSTR M_lpszClassName** eine Null-terminierte Zeichenfolge mit dem Namen der ASCII-Klasse.  
  
- **Int M_nObjectSize** die Größe des Objekts in Bytes. Wenn das Objekt, zeigen Sie auf die speicherbelegung Datenmember hat, ist die Größe dieses Speichers nicht enthalten.  
  
- **"Uint" M_wSchema** die Schema-Anzahl (-1 für nicht serialisierbare Klassen). Finden Sie unter der [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) Makro für eine Beschreibung des Schema-Anzahl.  
  
- **CObject\* (PASCAL\* CRuntimeClass) ()** einen Funktionszeiger Standardkonstruktor, der ein Objekt der Klasse erstellt (gültig nur, wenn die Klasse dynamische Erstellung unterstützt; andernfalls gibt **NULL** ).  
  
- **CRuntimeClass\* (PASCAL\* M_pfn_GetBaseClass) ()** Wenn Ihre Anwendung auf die AFXDLL-Version von MFC dynamisch verknüpft ist, ein Zeiger auf eine Funktion, die gibt die `CRuntimeClass` Struktur der Basisklasse.  
  
- **CRuntimeClass\* M_pBaseClass** Wenn Ihre Anwendung statisch mit MFC, ein Zeiger auf verknüpft ist die `CRuntimeClass` Struktur der Basisklasse.  
  
 Diese Funktion erfordert die Verwendung der [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate), oder [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) Makros in der klassenimplementierung. Andernfalls erhalten Sie falsche Ergebnisse.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) für eine Liste der `CAge` Klasse zur Verwendung in allen `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]  
  
##  <a name="iskindof"></a>  CObject:: IsKindOf  
 Testet, dieses Objekt Beziehung zu einer angegebenen Klasse.  
  
```  
BOOL IsKindOf(const CRuntimeClass* pClass) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pClass`  
 Ein Zeiger auf eine [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) zugeordnete Struktur Ihrer `CObject`-abgeleitete Klasse.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Objekt der Klasse entspricht; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion prüft `pClass` um festzustellen, ob (1) Es handelt sich um ein Objekt der angegebenen Klasse oder (2) Es handelt sich um ein Objekt einer Klasse, die von der angegebenen Klasse abgeleitet. Diese Funktion funktioniert nur für Klassen, die mit der [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic), [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate), oder [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) Makro.  
  
 Verwenden Sie diese Funktion nicht sehr häufig auf, da es die Polymorphie-Funktion von C++ unterlaufen kann. Verwenden Sie stattdessen virtuelle Funktionen.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) für eine Liste der `CAge` Klasse zur Verwendung in allen `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]  
  
##  <a name="isserializable"></a>  CObject::IsSerializable  
 Testet, ob dieses Objekt für die Serialisierung geeignet ist.  
  
```  
BOOL IsSerializable() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn dieses Objekt serialisiert werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Für eine Klasse, die serialisierbar sein, darf der Deklaration der [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) -Makro und die Implementierung darf die [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) Makro.  
  
> [!NOTE]
>  Überschreiben Sie diese Funktion nicht.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) für eine Liste der `CAge` Klasse zur Verwendung in allen `CObject` Beispiele.  
  
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
 In der Debugversion Operator **löschen** beteiligt ist, in eine Zuordnung Überwachung Schema entwickelt, um Speicherverluste zu erkennen.  
  
 Wenn Sie die Codezeile verwenden  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]  
  
 vor der Implementierung in einer. CPP-Datei, klicken Sie dann die dritte Version von **löschen** verwendet werden, die Anzahl Dateiname und die Zeilennummer in der belegten Blocks um später speichern. Sie müssen keine Gedanken machen, geben Sie die zusätzlichen Parameter; ein Makro übernimmt, die für Sie.  
  
 Auch wenn Sie nicht verwenden `DEBUG_NEW` im Debugmodus befindet, erhalten Sie weiterhin Erkennung von Speicherverlusten, jedoch ohne die Quelldatei Nummer der Zeile reporting oben beschrieben.  
  
 Wenn Sie Operatoren außer Kraft setzen **neue** und **löschen**, Sie communityimages diese Diagnose-Funktion.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) für eine Liste der `CAge` Klasse zur Verwendung in der `CObject` Beispiele.  
  
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
 In der Debugversion Operator **neue** beteiligt ist, in eine Zuordnung Überwachung Schema entwickelt, um Speicherverluste zu erkennen.  
  
 Wenn Sie die Codezeile verwenden  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]  
  
 vor der Implementierung in einer. CPP-Datei, klicken Sie dann die zweite Version der **neue** verwendet werden, die Anzahl Dateiname und die Zeilennummer in der belegten Blocks um später speichern. Sie müssen keine Gedanken machen, geben Sie die zusätzlichen Parameter; ein Makro übernimmt, die für Sie.  
  
 Auch wenn Sie nicht verwenden `DEBUG_NEW` im Debugmodus befindet, erhalten Sie weiterhin Erkennung von Speicherverlusten, jedoch ohne die Quelldatei Nummer der Zeile reporting oben beschrieben.  
  
> [!NOTE]
>  Wenn Sie diesen Operator überschreiben, müssen Sie auch überschreiben **löschen**. Verwenden Sie nicht die Standardbibliothek **_new_handler** Funktion.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) für eine Liste der `CAge` Klasse zur Verwendung in der `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]  
  
##  <a name="serialize"></a>  Einfügeoperatoren  
 Liest oder schreibt dieses Objekt aus einem oder in ein Archiv.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 `ar`  
 Ein `CArchive` zu an / von zu serialisierende Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Sie überschreiben müssen `Serialize` für jede Klasse, die Sie serialisieren möchten. Die überschriebene `Serialize` müssen rufen Sie zuerst die `Serialize` Funktion der Basisklasse.  
  
 Müssen Sie auch verwenden die [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) Makro in der Klassendeklaration, und Sie verwenden, muss die [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) Makros in der Implementierung.  
  
 Verwendung [CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) oder [CArchive::IsStoring](../../mfc/reference/carchive-class.md#isstoring) zu ermitteln, ob das Archiv laden oder speichern.  
  
 `Serialize` wird aufgerufen, indem [CArchive::ReadObject](../../mfc/reference/carchive-class.md#readobject) und [CArchive::WriteObject](../../mfc/reference/carchive-class.md#writeobject). Diese Funktionen zugeordnet sind die `CArchive` Operator zum Einfügen ( **< \<**) und Extraktionsoperator ( **>>**).  
  
 Beispiele für die Serialisierung finden Sie im Artikel [Serialisierung: Serialisieren eines Objekts](../../mfc/serialization-serializing-an-object.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) für eine Liste der `CAge` Klasse zur Verwendung in allen `CObject` Beispiele.  
  
 [!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



