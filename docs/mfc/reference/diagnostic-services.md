---
title: Diagnosedienste | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- diagnosis, diagnostic services
- diagnostic macros, list of general MFC
- services, diagnostic
- MFC, diagnostic services
- general diagnostic functions and variables
- diagnostics, diagnostic functions and variables
- diagnostics, list of general MFC
- diagnosis, diagnostic functions and variables
- diagnosis, list of general MFC
- general diagnostic macros in MFC
- diagnostic macros
- diagnostic services
- object diagnostic functions in MFC
- diagnostics, diagnostic services
- diagnostic functions and variables
ms.assetid: 8d78454f-9fae-49c2-88c9-d3fabd5393e8
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: b943ef8dd652df061965fe81ecc9c08115636141
ms.openlocfilehash: 0e83114e2e6f062b9cb2164cf71bb25792304de0
ms.lasthandoff: 04/04/2017

---
# <a name="diagnostic-services"></a>Diagnosedienste
Die Microsoft Foundation Class-Bibliothek bietet viele Diagnosedienste, die das Debuggen von Programmen erleichtern. Zu diesen Diagnosediensten zählen Makros und globale Funktionen, die Ihnen das Nachverfolgen der Speicherzuweisungen von Programmen, das Sichern des Inhalts von Objekten zur Laufzeit und das Ausgeben von Debugmeldungen zur Laufzeit ermöglichen. Die Makros und globalen Funktionen für Diagnosedienste gruppieren sich in die folgenden Kategorien:  
  
-   Allgemeine Diagnosemakros  
  
-   Allgemeine Diagnosefunktionen und -Variablen  
  
-   Objektdiagnosefunktionen  
  
 Diese Makros und Funktionen sind verfügbar für alle Klassen abgeleitet `CObject` in den Debug- und Versionen von MFC. Allerdings alle außer `DEBUG_NEW` und **überprüfen** nichts in der endgültigen Produktversion.  
  
 In der Debugbibliothek sind alle zugewiesenen Speicherblöcke mit einer Reihe von "Wächterbytes" geklammert. Wenn diese Bytes durch einen fehlerhaften Schreibzugriff auf den Speicher gestört werden, können die Diagnoseroutinen ein Speicherproblem melden. Wenn Sie diese Zeile:  
  
 [!code-cpp[NVC_MFCCObjectSample Nr. 14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 in Ihre Implementierungsdatei einschließen, alle Aufrufe von **neue** speichert der Dateiname und Zeilennummer angegeben, in dem die speicherzuweisung erfolgt. Die Funktion [CMemoryState](cmemorystate-structure.md#dumpallobjectssince) zeigt diese Zusatzinformationen, sodass Sie Speicherverluste zu identifizieren. Auch auf die Klasse verweisen [CDumpContext](../../mfc/reference/cdumpcontext-class.md) zusätzliche Informationen zur Diagnoseausgabe.  
  
 Darüber hinaus unterstützt die C-Laufzeitbibliothek auch eine Reihe von Diagnosefunktionen, die Sie zum Debuggen von Anwendungen verwenden können. Weitere Informationen finden Sie unter [Debugroutinen](../../c-runtime-library/debug-routines.md) in die Run-Time Library Reference.  
  
### <a name="mfc-general-diagnostic-macros"></a>Allgemeine MFC-Diagnosemakros  
  
|||  
|-|-|  
|[BESTÄTIGEN](#assert)|Eine Meldung ausgibt, und klicken Sie dann bricht das Programm ab, wenn der angegebene Ausdruck ergibt **"false"** in der Debugversion der Bibliothek.|  
|[ASSERT_KINDOF](#assert_kindof)|Prüft, ob ein Objekt ein Objekt der angegebenen Klasse oder einer aus der angegebenen Klasse abgeleiteten Klasse ist.|  
|[ASSERT_VALID](#assert_valid)|Testet die interne Gültigkeit eines Objekts durch Aufrufen seiner `AssertValid` Memberfunktion; in der Regel außer Kraft gesetzte aus `CObject`.|
|[DEBUG_NEW](#debug_new)|Gibt einen Dateinamen und eine Zeilennummer für alle Objektzuweisungen im Debugmodus an, um die Suche nach Speicherlecks zu unterstützen.|  
|[DEBUG_ONLY](#debug_only)|Ähnlich wie **ASSERT** jedoch keine Tests den Wert des Ausdrucks; nützlich für Code, der nur im Debugmodus ausgeführt werden soll.|  
|[Stellen Sie sicher und ENSURE_VALID](#ensure)|So überprüfen Sie die Richtigkeit der Daten verwenden.|
|[THIS_FILE](#this_file)|Wird erweitert, um den Namen der Datei, die kompiliert wird.|
|[TRACE](#trace)|Bietet `printf`--ähnliche Funktionalität in der Debugversion der Bibliothek.|  
|[VERGEWISSERN SIE SICH](#verify)|Ähnlich wie **ASSERT** jedoch wertet den Ausdruck in der Releaseversion der Bibliothek als auch in der Debugversion.|  
  
### <a name="mfc-general-diagnostic-variables-and-functions"></a>Allgemeine MFC-Diagnosevariablen und -Funktionen  
  
|||  
|-|-|  
|[afxDump](#afxdump)|Globale Variable, die sendet [CDumpContext](../../mfc/reference/cdumpcontext-class.md) Informationen an das debuggerausgabefenster oder das debugterminal.|  
|[afxMemDF](#afxmemdf)|Globale Variable, die das Verhalten der Debugspeicherzuweisung steuert.|  
|[AfxCheckError](#afxcheckerror)|Globale Variable, die zum Prüfen des übergebenen **SCODE** um festzustellen, ob es ein Fehler ist, und wenn dies der Fall ist, den entsprechenden Fehler löst.|  
|[AfxCheckMemory](#afxcheckmemory)|Überprüft die Integrität des gesamten derzeit zugewiesenen Speichers.|  
|[AfxDebugBreak](#afxdebugbreak)|Bewirkt, dass eine Unterbrechung in der Ausführung.|
|[AfxDump](#cdumpcontext_in_mfc)|Sichert bei einem Aufruf im Debugger den Status eines Objekts während des Debuggens.|  
|[AfxDump](#afxdump)|Interne Funktion, der den Zustand eines Objekts während des Debuggens einen Dump erstellt.|
|[AfxDumpStack](#afxdumpstack)|Generiert ein Image des aktuellen Stapels. Diese Funktion wird immer statisch gelinkt.|  
|[AfxEnableMemoryLeakDump](#afxenablememoryleakdump)|Ermöglicht das Sichern von Speicherlecks.|  
|[AfxEnableMemoryTracking](#afxenablememorytracking)|Aktiviert und deaktiviert die Arbeitsspeicher-Nachverfolgung.|  
|[AfxIsMemoryBlock](#afxismemoryblock)|Überprüft, ob ein Speicherblock ordnungsgemäß zugewiesen wurde.|  
|[AfxIsValidAddress](#afxisvalidaddress)|Überprüft, ob ein Speicheradressbereich innerhalb der Grenzen des Programms liegt.|  
|[AfxIsValidString](#afxisvalidstring)|Bestimmt, ob ein Zeiger auf eine Zeichenfolge gültig ist.|  
|[AfxSetAllocHook](#afxsetallochook)|Ermöglicht das Aufrufen einer Funktion für jede Speicherzuweisung.|  
  
### <a name="mfc-object-diagnostic-functions"></a>MFC-Objektdiagnosefunktionen  
  
|||  
|-|-|  
|[AfxDoForAllClasses](#afxdoforallclasses)|Führt eine bestimmte Funktion für alle `CObject`-abgeleitete Klassen, die typüberprüfung zur Laufzeit unterstützen.|  
|[AfxDoForAllObjects](#afxdoforallobjects)|Führt eine angegebene Funktion auf allen `CObject`-abgeleitete Objekte, die mit zugewiesen wurden **neue**.|  

### <a name="mfc-compilation-macros"></a>Kompilierung von MFC-Makros
|||
|-|-|
|[_AFX_SECURE_NO_WARNINGS](#afx_secure_no_warnings)|Unterdrückt die Compiler-Warnungen für die Verwendung von MFC-Funktionen, die als veraltet markierte.|  


## <a name="afx_secure_no_warnings"></a>_AFX_SECURE_NO_WARNINGS
Unterdrückt die Compiler-Warnungen für die Verwendung von MFC-Funktionen, die als veraltet markierte.  
   
### <a name="syntax"></a>Syntax   
```  
_AFX_SECURE_NO_WARNINGS  
```     
### <a name="example"></a>Beispiel  
 In diesem Codebeispiel würde eine compilerwarnung aus, wenn _AFX_SECURE_NO_WARNINGS nicht definiert wurden.  
  
 ```cpp
// define this before including any afx files in stdafx.h
#define _AFX_SECURE_NO_WARNINGS
```
```cpp
CRichEditCtrl* pRichEdit = new CRichEditCtrl;
pRichEdit->Create(WS_CHILD|WS_VISIBLE|WS_BORDER|ES_MULTILINE,
   CRect(10,10,100,200), pParentWnd, 1);
char sz[256];
pRichEdit->GetSelText(sz);
```

## <a name="afxdebugbreak"></a>AfxDebugBreak
Mit dieser Funktion können dazu führen, dass eine Unterbrechung (an der Position des Aufrufs von `AfxDebugBreak`) bei der Ausführung der Debugversion des MFC-Anwendung.  

### <a name="syntax"></a>Syntax    
```
void AfxDebugBreak( );    
```  
   
### <a name="remarks"></a>Hinweise  
 `AfxDebugBreak`wirkt sich nicht in Releaseversionen von MFC-Anwendung, und sollte entfernt werden. Diese Funktion sollte nur in MFC-Anwendungen verwendet werden. Verwenden Sie die Win32-API-Version **"DebugBreak"**, um eine Unterbrechung in MFC-fremden Anwendungen verursachen.  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxver_.h   

##  <a name="assert"></a>BESTÄTIGEN
 Wertet das Argument.  
  
```   
ASSERT(booleanExpression)   
```  
  
### <a name="parameters"></a>Parameter  
 `booleanExpression`  
 Gibt einen Ausdruck (einschließlich Zeigerwerte), der ungleich NULL oder 0 ergibt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Ergebnis 0 ist, wird das Makro gibt eine diagnosemeldung und bricht das Programm ab. Wenn die Bedingung ungleich NULL ist, wird keine Aktion ausgeführt.  
  
 Die Diagnosemeldung hat die Form  
  
 `assertion failed in file <name> in line <num>`  
  
 auf dem *Namen* ist der Name der Quelldatei, und *Num* wird die Zeilennummer der Assertion, die in der Quelldatei ist fehlgeschlagen.  
  
 In der endgültigen Produktversion von MFC **ASSERT** wird den Ausdruck nicht ausgewertet, und wird nicht das Programm unterbrochen. Wenn unabhängig von der Umgebung der Ausdruck ausgewertet werden muss, verwenden Sie die **überprüfen** Makro anstelle von **ASSERT**.  
  
> [!NOTE]
>  Diese Funktion ist nur in der Debugversion des MFC-verfügbar.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities #44](../../mfc/codesnippet/cpp/diagnostic-services_2.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="assert_kindof"></a>ASSERT_KINDOF  
 Dieses Makro wird bestätigt, dass das Objekt verweist, ein Objekt der angegebenen Klasse ist oder ist ein Objekt einer Klasse, die von der angegebenen Klasse abgeleitet.  
  
```   
ASSERT_KINDOF(classname, pobject)  
```  
  
### <a name="parameters"></a>Parameter  
 *Klassenname*  
 Der Name des eine `CObject`-Klasse.  
  
 *pObject*  
 Ein Zeiger auf ein Klassenobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Die *Pobject* Parameter muss ein Zeiger auf ein Objekt sein und darf **const**. Das Objekt verweist und die Klasse muss unterstützen `CObject` Laufzeit Klasseninformationen. Als Beispiel, um sicherzustellen, dass `pDocument` ist ein Zeiger auf ein Objekt von der `CMyDoc` Klasse oder eines seiner ableitungen können Sie code:  
  
 [!code-cpp[NVC_MFCDocView #194](../../mfc/codesnippet/cpp/diagnostic-services_3.cpp)]  
  
 Mithilfe der `ASSERT_KINDOF` -Makro ist identisch mit der Codierung:  
  
 [!code-cpp[NVC_MFCDocView #195](../../mfc/codesnippet/cpp/diagnostic-services_4.cpp)]  
  
 Diese Funktion funktioniert nur für Klassen, die mit dem [DECLARE_DYNAMIC] (Run-Time-Objekt-Modell-services.md #Declare_dynamic oder [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) Makro.  
  
> [!NOTE]
>  Diese Funktion ist nur in der Debugversion des MFC-verfügbar.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="assert_valid"></a>ASSERT_VALID  
 So testen Sie Ihre Annahmen über die Gültigkeit der interne Status eines Objekts verwenden.  
  
```   
ASSERT_VALID(pObject)   
```  
  
### <a name="parameters"></a>Parameter  
 `pObject`  
 Gibt ein Objekt einer Klasse abgeleitet `CObject` , die hat eine überschreibenden Version der `AssertValid` Memberfunktion.  
  
### <a name="remarks"></a>Hinweise  
 `ASSERT_VALID`Ruft die `AssertValid` -Memberfunktion des Objekts als Argument übergeben.  
  
 In der endgültigen Produktversion von MFC `ASSERT_VALID` wird keine Aktion ausgeführt. In der Debugversion überprüft den Zeiger, überprüft **NULL**, und ruft die eigenen `AssertValid` Memberfunktionen. Wenn eines dieser tests fehlschlägt, wird eine Warnmeldung angezeigt, auf die gleiche Weise wie [ASSERT](#assert).  
  
> [!NOTE]
>  Diese Funktion ist nur in der Debugversion des MFC-verfügbar.  
  
 Weitere Informationen und Beispiele finden Sie unter [MFC-Anwendungen Debuggen](/visualstudio/debugger/mfc-debugging-techniques).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample Nr. 19](../../mfc/codesnippet/cpp/diagnostic-services_5.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h

##  <a name="debug_new"></a>DEBUG_NEW  
 Suchen von Arbeitsspeicherverlusten unterstützt.  
  
```   
#define  new DEBUG_NEW   
```  
  
### <a name="remarks"></a>Hinweise  
 Können Sie `DEBUG_NEW` überall in Ihrem Programm, die Sie normalerweise verwenden würden die **neue** Operator, um die Heap-Speicher zu belegen.  
  
 Im Debugmodus befinden (wenn die **_DEBUG** Symbol definiert ist), `DEBUG_NEW` werden von nachverfolgt der Dateiname und die Zeilennummer für jede von ihm reservierten Objekts. Klicken Sie dann bei Verwendung der [CMemoryState](cmemorystate-structure.md#dumpallobjectssince) Memberfunktion, jedes Objekt zugeordnet `DEBUG_NEW` wird angezeigt mit der Dateiname und Zeilennummer, in denen es reserviert wurde.  
  
 Mit `DEBUG_NEW`, legen Sie die folgende Anweisung in Quelldateien:  
  
 [!code-cpp[NVC_MFCCObjectSample Nr. 14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 Nachdem Sie diese Direktive einfügen, wird der Präprozessor einfügen `DEBUG_NEW` ablegen, wo Sie verwenden **neue**, und MFC ist für den Rest. Wenn Sie eine Releaseversion des Programms kompilieren `DEBUG_NEW` aufgelöst wird, um eine einfache **neue** Vorgang und den Dateinamen und Zeilennummern werden nicht generiert.  
  
> [!NOTE]
>  In früheren Versionen von MFC (4.1 und früher) mussten Sie versetzen das `#define` Anweisung, nachdem alle Anweisungen, die aufgerufen der `IMPLEMENT_DYNCREATE` oder `IMPLEMENT_SERIAL` Makros. Dies ist nicht mehr erforderlich.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h

##  <a name="debug_only"></a>DEBUG_ONLY  
 Im Debugmodus befinden (wenn die **_DEBUG** Symbol definiert ist), `DEBUG_ONLY` wertet das Argument.  
  
```   
DEBUG_ONLY(expression)   
```  
  
### <a name="remarks"></a>Hinweise  
 In einem Releasebuild **DEBUG_ONLY** Argument wird nicht ausgewertet. Dies ist hilfreich, wenn Sie über Code verfügen, die nur in Debug-Builds ausgeführt werden soll.  
  
 Die `DEBUG_ONLY` Makro ist gleichbedeutend mit umgebenden *Ausdruck* mit **#ifdef _DEBUG** und `#endif`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities #32](../../mfc/codesnippet/cpp/diagnostic-services_6.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h

 ### <a name="ensure"></a>Stellen Sie sicher und ENSURE_VALID
So überprüfen Sie die Richtigkeit der Daten verwenden.  
   
### <a name="syntax"></a>Syntax    
```
ENSURE(  booleanExpression )  
ENSURE_VALID( booleanExpression  )  
```
### <a name="parameters"></a>Parameter  
 `booleanExpression`  
 Gibt einen booleschen Ausdruck, der darauf getestet werden.  
   
### <a name="remarks"></a>Hinweise  
 Diese Makros dient die Überprüfung von Parametern zu verbessern. Die Makros zu verhindern, dass die weitere Verarbeitung der falsche Parameter im Code. Im Gegensatz zu den **ASSERT** Makros, die **stellen Sie sicher** Makros löst eine Ausnahme neben dem Generieren einer Assertion.  
  
 Die Makros Verhalten auf zwei Arten entsprechend der Projektkonfiguration. Der Aufruf Makros **ASSERT** , und klicken Sie dann eine Ausnahme auslösen, wenn die Assertion fehlschlägt. Folglich in Debugkonfigurationen (d. h. **_DEBUG** definiert ist) die Makros erzeugen eine Assertion und die Ausnahme in der Release-Konfigurationen, die Makros zu erzeugen, nur die Ausnahme (**ASSERT** wertet den Ausdruck im Releasekonfigurationen nicht).  
  
 Das Makro **ENSURE_ARG** verhält sich wie die **sicherstellen, dass** Makro.  
  
 **ENSURE_VALID** Aufrufe der `ASSERT_VALID` Makro (die Auswirkungen nur in Debug-Builds aufweist). Darüber hinaus **ENSURE_VALID** löst eine Ausnahme aus, wenn der Zeiger NULL ist. Der NULL-Test wird im sowohl Debug- und Releasekonfigurationen ausgeführt.  
  
 Wenn eines dieser tests fehlschlägt, wird eine Warnmeldung angezeigt, auf die gleiche Weise wie **ASSERT**. Das Makro löst eine Ausnahme für ungültiges Argument aus, bei Bedarf.  
### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
   
### <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [VERGEWISSERN SIE SICH](#verify)   
 [ATLENSURE](#altensure)

## <a name="this_file"></a>THIS_FILE
Wird erweitert, um den Namen der Datei, die kompiliert wird.  
   
### <a name="syntax"></a>Syntax    
```
THIS_FILE    
```  
   
### <a name="remarks"></a>Hinweise  
 Die Informationen werden verwendet, indem Sie die **ASSERT** und **überprüfen** Makros. Die Anwendungs-Assistent und der Code-Assistenten platzieren Sie das Makro in Quellcodedateien, die sie erstellen.  
   
### <a name="example"></a>Beispiel  
```cpp
#ifdef _DEBUG
#undef THIS_FILE
static char THIS_FILE[] = __FILE__;
#endif

// __FILE__ is one of the six predefined ANSI C macros that the 
// compiler recognizes. 
```
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
   
### <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [BESTÄTIGEN](#assert)   
 [VERGEWISSERN SIE SICH](#verify)


##  <a name="trace"></a>TRACE  
 Sendet die angegebene Zeichenfolge an den Debugger von der aktuellen Anwendung.  
  
```   
TRACE(exp)  
TRACE(DWORD  category,  UINT  level, LPCSTR lpszFormat, ...)   
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [ATLTRACE2](http://msdn.microsoft.com/library/467ff555-e7a5-4f94-bdd9-50ee27ab9986) eine Beschreibung der **ABLAUFVERFOLGUNG**. **ABLAUFVERFOLGUNG** und `ATLTRACE2` weisen das gleiche Verhalten.  
  
 In der Debugversion von MFC sendet dieses Makro die angegebene Zeichenfolge an den Debugger von der aktuellen Anwendung. In einem Releasebuild kompiliert dieses Makro auf nichts verweist (kein Code überhaupt generiert).  
  
 Weitere Informationen finden Sie unter [MFC-Anwendungen Debuggen](/visualstudio/debugger/mfc-debugging-techniques).  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h

##  <a name="verify"></a>VERGEWISSERN SIE SICH  
 In der Debugversion von MFC wertet das Argument.  
  
```   
VERIFY(booleanExpression)   
```  
  
### <a name="parameters"></a>Parameter  
 `booleanExpression`  
 Gibt einen Ausdruck (einschließlich Zeigerwerte), der ungleich NULL oder 0 ergibt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Ergebnis 0 ist, wird das Makro gibt eine diagnosemeldung und hält das Programm an. Wenn die Bedingung ungleich NULL ist, wird keine Aktion ausgeführt.  
  
 Die Diagnosemeldung hat die Form  
  
 `assertion failed in file <name> in line <num>`  
  
 auf dem *Namen* ist der Name der Quelldatei und *Num* wird die Zeilennummer der Assertion, die in der Quelldatei ist fehlgeschlagen.  
  
 In der endgültigen Produktversion von MFC **überprüfen** wertet den Ausdruck aber nicht drucken oder das Programm unterbrochen. Z. B. wenn der Ausdruck einen Funktionsaufruf ist, wird der Aufruf vorgenommen werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView #198](../../mfc/codesnippet/cpp/diagnostic-services_7.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h

##  <a name="cdumpcontext_in_mfc"></a>AfxDump (CDumpContext in MFC)  
 Stellt grundlegende Objektdumps Funktion in Ihrer Anwendung bereit.  
  
```   
CDumpContext  afxDump;   
```  
  
### <a name="remarks"></a>Hinweise  
 `afxDump`ein vordefiniertes [CDumpContext](../../mfc/reference/cdumpcontext-class.md) -Objekt, das Sie senden kann `CDumpContext` Informationen in das Ausgabefenster des Debuggers oder an einem debugterminal. Geben Sie in der Regel `afxDump` als Parameter an `CObject::Dump`.  
  
 Unter Windows NT und allen Versionen von Windows `afxDump` Ausgabe wird an das Ausgabe-Debug-Fenster von Visual C++ gesendet, wenn die Anwendung zu debuggen.  
  
 Diese Variable wird nur in der Debugversion von MFC definiert. Weitere Informationen zu `afxDump`, finden Sie unter [MFC-Anwendungen Debuggen](/visualstudio/debugger/mfc-debugging-techniques).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities #23](../../mfc/codesnippet/cpp/diagnostic-services_8.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h


## <a name="afxdump"></a>AfxDump (intern)
Interne Funktion, den MFC verwendet, um den Status eines Objekts während des Debuggens zu speichern.  

### <a name="syntax"></a>Syntax    
```
void AfxDump(const CObject* pOb);   
```
### <a name="parameters"></a>Parameter  
 `pOb`  
 Ein Zeiger auf ein Objekt einer Klasse abgeleitet `CObject`.  
   
### <a name="remarks"></a>Hinweise  
 **AfxDump** Ruft ein Objekt `Dump` Memberfunktion und sendet die Informationen zum Speicherort, durch angegeben die `afxDump` Variable. **AfxDump** steht nur in der Debugversion von MFC.  
  
 Programmcode sollte nicht aufrufen **AfxDump**, sondern rufen stattdessen sollte die `Dump` Memberfunktion des entsprechenden Objekts.  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
   
### <a name="see-also"></a>Siehe auch  
 [CObject::Dump](cobject-class.md#dump)   



##  <a name="afxmemdf"></a>afxMemDF  
 Diese Variable wird der Zugriff über einen Debugger oder das Programm und Ihnen Allocation-Diagnose zu optimieren.  
  
```   
int  afxMemDF;  
```  
  
### <a name="remarks"></a>Hinweise  
 `afxMemDF`können die folgenden Werte entsprechend den Angaben von der Aufzählung `afxMemDF`:  
  
- **AllocMemDF** aktiviert die debugging-Zuweisung (in der Debugbibliothek Standardeinstellung).  
  
- **DelayFreeMemDF** Speicherfreigabe verzögert. Während das Programm einen Speicherblock frei, gibt die Zuweisung, dass der Arbeitsspeicher nicht an das zugrunde liegende Betriebssystem zurück. Dies wird auf das Programm Maximaler Arbeitsspeicher Belastung platziert werden.  
  
- **CheckAlwaysMemDF** Aufrufe `AfxCheckMemory` jedes Mal, wenn Arbeitsspeicher reserviert oder freigegeben wird. Dies wird erheblich beeinträchtigt, speicherbelegungen und Aufhebungen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities #30](../../mfc/codesnippet/cpp/diagnostic-services_9.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h

##  <a name="afxcheckerror"></a>AfxCheckError  
 Diese Funktion prüft das übergebene **SCODE** um festzustellen, ob ein Fehler.  
  
```   
void AFXAPI AfxCheckError(SCODE sc);
throw CMemoryException* 
throw COleException*  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn es sich um einen Fehler handelt, löst die Funktion eine Ausnahme aus. Wenn der übergebene `SCODE` ist **E_OUTOFMEMORY**, löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) durch Aufrufen von [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception). Andernfalls löst die Funktion eine [COleException](../../mfc/reference/coleexception-class.md) durch Aufrufen von [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 Diese Funktion kann verwendet werden, um die Rückgabewerte für Aufrufe von OLE-Funktionen in Ihrer Anwendung zu überprüfen. Den Rückgabewert mit dieser Funktion in Ihrer Anwendung testen, können Sie ordnungsgemäß auf fehlerbedingungen mit einer minimalen Menge an Code reagieren.  
  
> [!NOTE]
>  Diese Funktion hat dieselbe Wirkung im Debugmodus, und nicht-Debugbuilds.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer #33](../../mfc/codesnippet/cpp/diagnostic-services_10.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h

##  <a name="afxcheckmemory"></a>AfxCheckMemory  
 Diese Funktion überprüft den freien Speicherpool und gibt Fehlermeldungen nach Bedarf.  
  
```   
BOOL  AfxCheckMemory(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn keine Speicherfehler; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Funktion keine Speicherschäden erkennt, wird nichts ausgegeben.  
  
 Alle Speicherblöcke, die derzeit auf dem Heap reserviert werden überprüft, einschließlich der vom zugeordneten **neue** aber nicht diejenigen, die durch direkte Aufrufe von zugrunde liegenden speicherzuordnungen, wie z. B. die `malloc` Funktion oder die **GlobalAlloc** Windows-Funktion. Wenn Sie einen beliebigen Textblock gefunden wird, ist möglicherweise beschädigt, wird eine Nachricht an die Debuggerausgabe gedruckt.  
  
 Wenn Sie die Zeile einschließen  
  
 [!code-cpp[NVC_MFCCObjectSample Nr. 14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 in einem Programmmodul, klicken Sie dann bei nachfolgenden Aufrufen `AfxCheckMemory` Anzeigen der Dateiname und Zeilennummer angegeben, in dem der Speicher belegt wurde.  
  
> [!NOTE]
>  Wenn Ihr Modul enthält ein oder mehrere Implementierungen von serialisierbare Klassen, darf höchstens die `#define` Zeile nach dem letzten `IMPLEMENT_SERIAL` Makro-Aufruf.  
  
 Diese Funktion funktioniert nur in der Debugversion von MFC.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample #26](../../mfc/codesnippet/cpp/diagnostic-services_11.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
 
##  <a name="afxdump"></a>AfxDump (MFC)  
 Mit dieser Funktion wird im Debugger, um den Status eines Objekts während des Debuggens zu speichern.  
  
```   
void AfxDump(const CObject* pOb); 
```  
  
### <a name="parameters"></a>Parameter  
 `pOb`  
 Ein Zeiger auf ein Objekt einer Klasse abgeleitet `CObject`.  
  
### <a name="remarks"></a>Hinweise  
 **AfxDump** Ruft ein Objekt `Dump` Memberfunktion und sendet die Informationen zum Speicherort, durch angegeben die `afxDump` Variable. **AfxDump** steht nur in der Debugversion von MFC.  
  
 Programmcode sollte nicht aufrufen **AfxDump**, sondern rufen stattdessen sollte die `Dump` Memberfunktion des entsprechenden Objekts.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  

### <a name="see-also"></a>Siehe auch  
 [CObject::Dump](cobject-class.md#dump)   


  
##  <a name="afxdumpstack"></a>AfxDumpStack  
 Dieser globale Funktion kann verwendet werden, um ein Bild des aktuellen Stapels zu generieren.  
  
```   
void AFXAPI AfxDumpStack(DWORD dwTarget = AFX_STACK_DUMP_TARGET_DEFAULT); 
```  
  
### <a name="parameters"></a>Parameter  
 *dwTarget*  
 Gibt an, das Ziel der Dump ausgegeben. Mögliche Werte, die mit dem bitweisen OR kombiniert werden können ( **|**)-Operator, lauten wie folgt:  
  
- **AFX_STACK_DUMP_TARGET_TRACE** sendet die Ausgabe von der die [TRACE](#trace) Makro. Die **TRACE** Makro generiert eine Ausgabe in Debugversionen nur; er generiert keine Ausgabe in Releasebuilds. Darüber hinaus **ABLAUFVERFOLGUNG** an andere Ziele neben der Debugger umgeleitet werden können.  
  
- **AFX_STACK_DUMP_TARGET_DEFAULT** sendet dump Ausgabe an das Standardziel. Für einen Debugbuild Ausgabe wird an die **TRACE** Makro. In einem Releasebuild erfolgt die Ausgabe in die Zwischenablage.  
  
- **AFX_STACK_DUMP_TARGET_CLIPBOARD** sendet die Ausgabe in die Zwischenablage nur. Befindet sich die Daten in der Zwischenablage als nur-Text mithilfe der **HIERSVR** Format der Zwischenablage.  
  
- **AFX_STACK_DUMP_TARGET_BOTH** sendet die Ausgabe in die Zwischenablage und zu den **ABLAUFVERFOLGUNG** -Makro, gleichzeitig.  
  
- **AFX_STACK_DUMP_TARGET_ODS** sendet die Ausgabe direkt an den Debugger über die Win32-Funktion **OutputDebugString()**. Diese Option generiert Debuggerausgabe in sowohl Debug- und Releasebuilds, wenn ein Debugger an den Prozess angefügt ist. **AFX_STACK_DUMP_TARGET_ODS** immer erreicht den Debugger, (falls es angefügt wird) und können nicht umgeleitet werden.  
  
### <a name="remarks"></a>Hinweise  
 Das folgende Beispiel gibt eine einzige Codezeile die aufrufenden generierte Ausgabe wieder `AfxDumpStack` aus einem Schaltflächenhandler in einer MFC-Dialogfeld Anwendung:  
  
 `=== begin AfxDumpStack output ===`  
  
 `00427D55: DUMP2\DEBUG\DUMP2.EXE! void AfxDumpStack(unsigned long) + 181 bytes`  
  
 `0040160B: DUMP2\DEBUG\DUMP2.EXE! void CDump2Dlg::OnClipboard(void) + 14 bytes`  
  
 `0044F884: DUMP2\DEBUG\DUMP2.EXE! int _AfxDispatchCmdMsg(class CCmdTarget *,`  
  
 `unsigned int,int,void ( CCmdTarget::*)(void),void *,unsigned int,struct AFX_CMDHANDLE`  
  
 `0044FF7B: DUMP2\DEBUG\DUMP2.EXE! virtual int CCmdTarget::OnCmdMsg(unsigned`  
  
 `int,int,void *,struct AFX_CMDHANDLERINFO *) + 626 bytes`  
  
 `00450C71: DUMP2\DEBUG\DUMP2.EXE! virtual int CDialog::OnCmdMsg(unsigned`  
  
 `int,int,void *,struct AFX_CMDHANDLERINFO *) + 36 bytes`  
  
 `00455B27: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnCommand(unsigned`  
  
 `int,long) + 312 bytes`  
  
 `00454D3D: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnWndMsg(unsigned`  
  
 `int,unsigned int,long,long *) + 83 bytes`  
  
 `00454CC0: DUMP2\DEBUG\DUMP2.EXE! virtual long CWnd::WindowProc(unsigned`  
  
 `int,unsigned int,long) + 46 bytes`  
  
 `004528D9: DUMP2\DEBUG\DUMP2.EXE! long AfxCallWndProc(class CWnd *,struct`  
  
 `HWND__ *,unsigned int,unsigned int,long) + 237 bytes`  
  
 `00452D34: DUMP2\DEBUG\DUMP2.EXE! long AfxWndProc(struct HWND__ *,unsigned`  
  
 `int,unsigned int,long) + 129 bytes`  
  
 `BFF73663: WINDOWS\SYSTEM\KERNEL32.DLL! ThunkConnect32 + 2148 bytes`  
  
 `BFF928E0: WINDOWS\SYSTEM\KERNEL32.DLL! UTUnRegister + 2492 bytes`  
  
 `=== end AfxDumpStack() output ===`  
  
 Jede Zeile in der obigen Ausgabe gibt die Adresse des letzten Funktionsaufrufs, der vollständige Pfadname des Moduls, enthält der Aufruf der Funktion und der Funktionsprototyp aufgerufen. Wenn der Funktionsaufruf auf dem Stapel nicht an die genaue Adresse der Funktion geschieht, wird ein Offset von Bytes angezeigt.  
  
 Die folgende Tabelle beschreibt z. B. die erste Zeile des obigen Ausgabe:  
  
|Ausgabe|Beschreibung|  
|------------|-----------------|  
|`00427D55:`|Die Rückgabeadresse der dem letzten Funktionsaufruf.|  
|`DUMP2\DEBUG\DUMP2.EXE!`|Der vollständige Pfadname des Moduls, das den Funktionsaufruf enthält.|  
|`void AfxDumpStack(unsigned long)`|Der Funktionsprototyp aufgerufen.|  
|`+ 181 bytes`|Der Offset in Bytes, die von der Adresse der Funktionsprototypen (in diesem Fall `void AfxDumpStack(unsigned long)`) an die Rücksendeadresse (in diesem Fall `00427D55`).|  
  
 `AfxDumpStack`ist im Debug- und aufgeführt Versionen der MFC-Bibliotheken verfügbar. Allerdings ist die Funktion immer statisch, verknüpft, auch wenn die ausführbare Datei in eine freigegebene DLL MFC verwendet. Die Funktion ist in gemeinsam genutzte Bibliothek Implementierungen in der MFCS42 gefunden. LIB-Bibliothek (und seine Varianten).  
  
 Diese Funktion wurde erfolgreich zu verwenden:  
  
-   Die Datei IMAGEHLP. DLL muss auf Ihrem Pfad befinden. Wenn Sie nicht über diese DLL verfügen, wird die Funktion eine Fehlermeldung angezeigt. Finden Sie unter [Bildbibliothek Hilfe](http://msdn.microsoft.com/library/windows/desktop/ms680321) Informationen auf den von IMAGEHLP bereitgestellten Funktion.  
  
-   Die Module, die auf dem Stapel Frames haben müssen Debuginformationen enthalten. Wenn sie keine Debuginformationen enthalten, die Funktion generiert immer noch eine stapelüberwachung, aber die Ablaufverfolgung weniger detailliert.  
### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="afxenablememoryleakdump"></a>AfxEnableMemoryLeakDump  
 Aktiviert und deaktiviert im Destruktor `AFX_DEBUG_STATE` die Ausgabe von Speicherverlusten.  
  
```  
BOOL AFXAPI AfxEnableMemoryLeakDump(BOOL bDump);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bDump`  
 `TRUE` gibt an, dass das Speicherabbild des Arbeitsspeicherverlusts aktiviert ist. `FALSE` gibt an, dass das Speicherabbild des Arbeitsspeicherverlusts deaktiviert ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherige Wert für dieses Flag.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Anwendung die MFC-Bibliothek entlädt, führt die MFC-Bibliothek eine Überprüfung auf Speicherverluste aus. An diesem Punkt werden alle von Arbeitsspeicherverlusten gemeldet, für den Benutzer über die **Debuggen** Fenster [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)].  
  
 Wenn Ihre Anwendung eine andere Bibliothek vor der MFC-Bibliothek lädt, werden einige Speicherbelegungen in dieser Bibliothek fälschlicherweise als Arbeitsspeicherverluste gemeldet. Wegen Arbeitsspeicherverlusten, die eigentlich keine sind, wird Ihre Anwendung möglicherweise langsam beendet, da die MFC-Bibliothek die Speicherverluste meldet. Verwenden Sie in diesem Fall `AfxEnableMemoryLeakDump` , um das Speicherabbild des Arbeitsspeicherverlusts zu deaktivieren.  
  
> [!NOTE]
>  Wenn Sie diese Methode verwenden, um das Speicherabbild des Arbeitsspeicherverlusts deaktivieren, erhalten Sie keine Berichte über tatsächliche Arbeitsspeicherverluste in Ihrer Anwendung. Sie sollten diese Methode nur verwenden, wenn Sie sicher sind, dass der Bericht über die Arbeitsspeicherverluste falsche Meldungen enthält.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="afxenablememorytracking"></a>AfxEnableMemoryTracking  
 Diagnose speicherüberwachung ist normalerweise in der Debugversion von MFC aktiviert.  
  
```   
BOOL AfxEnableMemoryTracking(BOOL bTrack); 
```  
  
### <a name="parameters"></a>Parameter  
 *bTrack*  
 Wenn dieser Wert auf **"true"** aktiviert die speicherüberwachung; **"False"** wird dadurch deaktiviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherige Einstellung des Flags Überwachung aktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um die Überwachung auf Abschnitte des Codes zu deaktivieren, die Sie kennen Blöcke ordnungsgemäß zugeordnet werden.  
  
 Weitere Informationen zu `AfxEnableMemoryTracking`, finden Sie unter [MFC-Anwendungen Debuggen](/visualstudio/debugger/mfc-debugging-techniques).  
  
> [!NOTE]
>  Diese Funktion funktioniert nur in der Debugversion von MFC.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities #24](../../mfc/codesnippet/cpp/diagnostic-services_12.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="afxismemoryblock"></a>AfxIsMemoryBlock  
 Testet eine Speicheradresse, um sicherzustellen, dass es stellt einen derzeit aktiven Speicherblock, der von der Diagnose Version der belegt wurde **neue**.  
  
```   
BOOL AfxIsMemoryBlock(
    const void* p,  
    UINT nBytes,  
    LONG* plRequestNumber = NULL); 
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Verweist auf den Speicherblock, der darauf getestet werden.  
  
 `nBytes`  
 Enthält die Länge des Speicherblocks in Bytes.  
  
 `plRequestNumber`  
 Verweist auf eine **lange** ganze Zahl, die sich mit den Speicherblock Zuordnung Sequenznummer ausgefüllt oder NULL, wenn er keine aktiven Speicherblocks darstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Speicherblock derzeit belegt ist und die Länge korrekt ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Er überprüft auch die angegebene Größe für die ursprüngliche zugeordnete Größe. Wenn die Funktion ungleich NULL zurückgibt, wird die Sequenznummer der Zuordnung zurückgegeben, `plRequestNumber`. Diese Zahl stellt die Reihenfolge, in dem der Block, im Vergleich zu allen anderen belegt wurde **neue** Zuordnungen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities #27](../../mfc/codesnippet/cpp/diagnostic-services_13.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="afxisvalidaddress"></a>AfxIsValidAddress  
 Testet alle Speicheradresse, um sicherzustellen, dass er vollständig innerhalb der Anwendung belegten Speicherplatz enthalten ist.  
  
```   
BOOL AfxIsValidAddress(
    const void* lp,  
    UINT nBytes,  
    BOOL bReadWrite = TRUE); 
```  
  
### <a name="parameters"></a>Parameter  
 `lp`  
 Verweist auf die Speicheradresse getestet werden.  
  
 `nBytes`  
 Enthält die Anzahl der Bytes an Arbeitsspeicher, der darauf getestet werden.  
  
 *bReadWrite*  
 Gibt an, ob der Arbeitsspeicher sowohl zum Lesen und Schreiben ( **"true"**) oder nur lesen ( **"false"**).  
  
### <a name="return-value"></a>Rückgabewert  
 Debug-Builds ist ungleich NULL, wenn die angegebene Arbeitsspeichergröße blockieren vollständig innerhalb der Anwendung belegten Speicherplatz enthalten; andernfalls 0.  
  
 In nichtdebugversionen einen Wert ungleich NULL `lp` nicht NULL ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Adresse ist nicht beschränkt auf Blöcke, die vom zugeordneten **neue**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities #28](../../mfc/codesnippet/cpp/diagnostic-services_14.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="afxisvalidstring"></a>AfxIsValidString  
 Verwenden Sie diese Funktion, um zu bestimmen, ob ein Zeiger auf eine Zeichenfolge gültig ist.  
  
```   
BOOL  AfxIsValidString(
    LPCSTR lpsz,  
    int nLength = -1); 
```  
  
### <a name="parameters"></a>Parameter  
 `lpsz`  
 Der Zeiger auf das Testen.  
  
 `nLength`  
 Gibt die Länge der Zeichenfolge, die getestet werden, in Bytes. Der Wert-1 gibt an, dass die Zeichenfolge Null-terminiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 In Debugbuilds ungleich NULL, wenn der angegebene Zeiger auf eine Zeichenfolge der angegebenen Größe verweist; andernfalls 0.  
  
 In nichtdebugversionen einen Wert ungleich NULL `lpsz` nicht NULL ist; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities #29](../../mfc/codesnippet/cpp/diagnostic-services_15.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="afxsetallochook"></a>AfxSetAllocHook  
 Legt einen Hook, der Aufrufen der angegebenen Funktion ermöglicht, bevor jeder Speicherblock belegt wird.  
  
```   
AFX_ALLOC_HOOK AfxSetAllocHook(AFX_ALLOC_HOOK pfnAllocHook); 
```  
  
### <a name="parameters"></a>Parameter  
 *pfnAllocHook*  
 Gibt den Namen der aufzurufenden Funktion. Finden Sie unter den Hinweisen für den Prototyp einer Zuordnung-Funktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn Sie die Zuordnung erlauben möchten; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Microsoft Foundation Class-Bibliothek Debug-Speicherreservierungsfunktion kann die Benutzer eine speicherbelegung zu überwachen und zu steuern, ob die Zuordnung zulässig ist eine benutzerdefinierte Hookfunktion aufrufen. Nachfolgend sind Reservierungshookfunktionen Prototyp:  
  
 **BOOL AFXAPI AllocHook( size_t** `nSize`**, BOOL** `bObject`**, LONG** `lRequestNumber` **);**  
  
 `nSize`  
 Die Größe der vorgeschlagenen speicherbelegung.  
  
 `bObject`  
 **"True"** ist die Zuordnung für einen `CObject`-abgeleitetes Objekt; andernfalls **"false"**.  
  
 `lRequestNumber`  
 Sequenznummer der speicherbelegung.  
  
 Beachten Sie, dass die **AFXAPI** -Aufrufkonvention gibt an, dass der aufgerufene die Parameter aus dem Stapel entfernen muss.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="afxdoforallclasses"></a>AfxDoForAllClasses  
 Ruft die angegebene Iteration-Funktion für alle serialisierbaren `CObject`-abgeleitete Klassen in der Anwendung belegten Speicherplatz.  
  
```   
void  
AFXAPI AfxDoForAllClasses(
    void (* pfn)(const CRuntimeClass* pClass, void* pContext),  
    void* pContext); 
```  
  
### <a name="parameters"></a>Parameter  
 `pfn`  
 Zeigt auf eine Iteration-Funktion für jede Klasse aufgerufen werden. Die Funktionsargumente sind ein Zeiger auf eine `CRuntimeClass` -Objekt und einen void-Zeiger auf zusätzliche Daten, die der Aufrufer der Funktion angibt.  
  
 `pContext`  
 Verweist auf optionale Daten, die der Aufrufer der Funktion für die Iteration bereitstellen kann. This-Zeiger kann **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Serialisierbare `CObject`-abgeleitete Klassen sind Klassen, die abgeleitet, mit der `DECLARE_SERIAL` Makro. Der Zeiger, der an übergebene `AfxDoForAllClasses` in `pContext` wird jedes Mal aufgerufen wird an die angegebene Iteration-Funktion übergeben.  
  
> [!NOTE]
>  Diese Funktion funktioniert nur in der Debugversion von MFC.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections #113](../../mfc/codesnippet/cpp/diagnostic-services_16.cpp)]  
  
 [!code-cpp[NVC_MFCCollections #114](../../mfc/codesnippet/cpp/diagnostic-services_17.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="afxdoforallobjects"></a>AfxDoForAllObjects  
 Führt die angegebene Iteration-Funktion für alle Objekte von einer abgeleiteten `CObject` mit verbraucht wurden **neue**.  
  
```   
void AfxDoForAllObjects(
    void (* pfn)(CObject* pObject, void* pContext),  
    void* pContext); 
```  
  
### <a name="parameters"></a>Parameter  
 `pfn`  
 Verweist auf eine Iteration-Funktion, die für jedes Objekt ausgeführt. Die Funktionsargumente sind ein Zeiger auf eine `CObject` und einen void-Zeiger auf zusätzliche Daten, die der Aufrufer der Funktion angibt.  
  
 `pContext`  
 Verweist auf optionale Daten, die der Aufrufer der Funktion für die Iteration bereitstellen kann. This-Zeiger kann **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Stapel, globalen oder eingebettete Objekte werden nicht aufgezählt. Der Zeiger übergeben wird, um `AfxDoForAllObjects` in `pContext` wird jedes Mal aufgerufen wird an die angegebene Iteration-Funktion übergeben.  
  
> [!NOTE]
>  Diese Funktion funktioniert nur in der Debugversion von MFC.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections #115](../../mfc/codesnippet/cpp/diagnostic-services_18.cpp)]  
  
 [!code-cpp[NVC_MFCCollections #116](../../mfc/codesnippet/cpp/diagnostic-services_19.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
