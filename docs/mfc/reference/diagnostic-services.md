---
title: Diagnosedienste | Microsoft-Dokumentation
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 86fe366a4d7863fb9339b7b5a9f880103876de33
ms.lasthandoff: 02/24/2017

---
# <a name="diagnostic-services"></a>Diagnosedienste
Die Microsoft Foundation Class-Bibliothek bietet viele Diagnosedienste, die das Debuggen von Programmen erleichtern. Zu diesen Diagnosediensten zählen Makros und globale Funktionen, die Ihnen das Nachverfolgen der Speicherzuweisungen von Programmen, das Sichern des Inhalts von Objekten zur Laufzeit und das Ausgeben von Debugmeldungen zur Laufzeit ermöglichen. Die Makros und globalen Funktionen für Diagnosedienste gruppieren sich in die folgenden Kategorien:  
  
-   Allgemeine Diagnosemakros  
  
-   Allgemeine Diagnosefunktionen und -Variablen  
  
-   Objektdiagnosefunktionen  
  
 Diese Makros und Funktionen sind für alle Klassen abgeleitet verfügbar `CObject` in den Debug- und Versionen von MFC. Allerdings alle außer `DEBUG_NEW` und **überprüfen** nichts in der endgültigen Produktversion.  
  
 In der Debugbibliothek sind alle zugewiesenen Speicherblöcke mit einer Reihe von "Wächterbytes" geklammert. Wenn diese Bytes durch einen fehlerhaften Schreibzugriff auf den Speicher gestört werden, können die Diagnoseroutinen ein Speicherproblem melden. Wenn Sie diese Zeile:  
  
 [!code-cpp[NVC_MFCCObjectSample&14;](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 in der Implementierungsdatei alle Aufrufe von **neue** speichert der Dateiname und Zeilennummer angegeben, in dem die Speicherzuordnungs stattgefunden hat. Die Funktion [CMemoryState](cmemorystate-structure.md#dumpallobjectssince) zeigt diese zusätzlichen Informationen, sodass Sie Speicherverluste zu identifizieren. Siehe auch die Klasse [CDumpContext](../../mfc/reference/cdumpcontext-class.md) Weitere Informationen zur Diagnose Ausgabe.  
  
 Darüber hinaus unterstützt die C-Laufzeitbibliothek auch eine Reihe von Diagnosefunktionen, die Sie zum Debuggen von Anwendungen verwenden können. Weitere Informationen finden Sie unter [Debuggen Routinen](../../c-runtime-library/debug-routines.md) in der Run-Time Library Reference.  
  
### <a name="mfc-general-diagnostic-macros"></a>Allgemeine MFC-Diagnosemakros  
  
|||  
|-|-|  
|[BESTÄTIGEN](#assert)|Wird eine Meldung ausgegeben, und klicken Sie dann das Programm abbricht, wenn der angegebene Ausdruck ergibt **FALSE** in der Debugversion der Bibliothek.|  
|[ASSERT_KINDOF](#assert_kindof)|Prüft, ob ein Objekt ein Objekt der angegebenen Klasse oder einer aus der angegebenen Klasse abgeleiteten Klasse ist.|  
|[ASSERT_VALID](#assert_valid)|Testet die interne Gültigkeit eines Objekts durch Aufrufen seiner `AssertValid` Memberfunktion; in der Regel von überschriebenen `CObject`.|  
|[DEBUG_NEW](#debug_new)|Gibt einen Dateinamen und eine Zeilennummer für alle Objektzuweisungen im Debugmodus an, um die Suche nach Speicherlecks zu unterstützen.|  
|[DEBUG_ONLY](#debug_only)|Ähnlich wie **ASSERT** jedoch nicht auf den Wert des Ausdrucks; testet sinnvoll für Code, der nur im Debugmodus ausgeführt werden soll.|  
|[TRACE](#trace)|Bietet `printf`-Funktion in der Debugversion der Bibliothek wie.|  
|[VERGEWISSERN SIE SICH](#verify)|Ähnlich wie **ASSERT** jedoch wertet den Ausdruck in der Releaseversion der Bibliothek sowie die Debugversion.|  
  
### <a name="mfc-general-diagnostic-variables-and-functions"></a>Allgemeine MFC-Diagnosevariablen und -Funktionen  
  
|||  
|-|-|  
|[afxDump](#afxdump)|Globale Variable, die sendet [CDumpContext](../../mfc/reference/cdumpcontext-class.md) Informationen in das Ausgabefenster des Debuggers oder das Debug-Terminal.|  
|[afxMemDF](#afxmemdf)|Globale Variable, die das Verhalten der Debugspeicherzuweisung steuert.|  
|[AfxCheckError](#afxcheckerror)|Globale Variable verwendet, um das übergebene **SCODE** um festzustellen, ob es einen Fehler, und wenn dies der Fall ist, den entsprechenden Fehler löst.|  
|[AfxCheckMemory](#afxcheckmemory)|Überprüft die Integrität des gesamten derzeit zugewiesenen Speichers.|  
|[AfxDump](#cdumpcontext_in_mfc_)|Sichert bei einem Aufruf im Debugger den Status eines Objekts während des Debuggens.|  
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
|[AfxDoForAllClasses](#afxdoforallclasses)|Führt eine angegebene Funktion auf allen `CObject`-abgeleitete Klassen, die die Überprüfung zur Laufzeit Typen unterstützen.|  
|[AfxDoForAllObjects](#afxdoforallobjects)|Führt eine angegebene Funktion auf allen `CObject`-abgeleitete Objekte, die mit zugeordnet wurden **neue**.|  
  
##  <a name="a-nameasserta--assert"></a><a name="assert"></a>BESTÄTIGEN
 Wertet das Argument.  
  
```   
ASSERT(booleanExpression)   
```  
  
### <a name="parameters"></a>Parameter  
 `booleanExpression`  
 Gibt einen Ausdruck (einschließlich Zeiger), der einen Wert ungleich NULL oder 0 ergibt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Ergebnis 0 ist, wird das Makro druckt eine diagnosemeldung und bricht das Programm ab. Wenn die Bedingung einen Wert ungleich NULL ist, wird keine Aktion ausgeführt.  
  
 Die Diagnosemeldung hat die Form  
  
 `assertion failed in file <name> in line <num>`  
  
 wobei *Namen* ist der Name der Quelldatei, und *Num* wird die Zeilennummer der Assertion ist, in der Quelldatei Fehler.  
  
 In der Releaseversion von MFC **ASSERT** wird den Ausdruck nicht ausgewertet, und daher wird das Programm unterbrochen. Wenn Sie unabhängig von der Umgebung der Ausdruck ausgewertet werden muss, verwenden Sie die **überprüfen** Makro anstelle von **ASSERT**.  
  
> [!NOTE]
>  Diese Funktion steht nur in der Debugversion von MFC.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities&#44;](../../mfc/codesnippet/cpp/diagnostic-services_2.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="a-nameassertkindofa--assertkindof"></a><a name="assert_kindof"></a>ASSERT_KINDOF  
 Dieses Makro wird bestätigt, dass das Objekt, auf ein Objekt der angegebenen Klasse ist ein Objekt einer Klasse, die von der angegebenen Klasse abgeleitet.  
  
```   
ASSERT_KINDOF(classname, pobject)  
```  
  
### <a name="parameters"></a>Parameter  
 *Klassenname*  
 Der Name des eine `CObject`-Klasse.  
  
 *pObject*  
 Ein Zeiger auf ein Objekt der Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Die *Pobject* Parameter muss ein Zeiger auf ein Objekt und kann **const**. Das Objekt verweist und die Klasse muss unterstützen `CObject` Laufzeit Klasseninformationen. Als Beispiel, um sicherzustellen, dass `pDocument` ist ein Zeiger auf ein Objekt der `CMyDoc` Klasse oder ihrer ableitungen können Sie code:  
  
 [!code-cpp[NVC_MFCDocView&#194;](../../mfc/codesnippet/cpp/diagnostic-services_3.cpp)]  
  
 Mithilfe der `ASSERT_KINDOF` -Makro ist identisch mit der Codierung:  
  
 [!code-cpp[NVC_MFCDocView&#195;](../../mfc/codesnippet/cpp/diagnostic-services_4.cpp)]  
  
 Diese Funktion ist nur für Klassen, die mit dem [DECLARE_DYNAMIC] (Run-Time-Objekt-Modell-services.md #Declare_dynamic oder [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) Makro.  
  
> [!NOTE]
>  Diese Funktion steht nur in der Debugversion von MFC.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="a-nameassertvalida--assertvalid"></a><a name="assert_valid"></a>ASSERT_VALID  
 So testen Sie Ihre Annahmen über die Gültigkeit des internen Zustand eines Objekts verwenden.  
  
```   
ASSERT_VALID(pObject)   
```  
  
### <a name="parameters"></a>Parameter  
 `pObject`  
 Gibt ein Objekt einer Klasse, die von abgeleiteten `CObject` , bei dem eine überschreibende Version der der `AssertValid` Member-Funktion.  
  
### <a name="remarks"></a>Hinweise  
 `ASSERT_VALID`Ruft die `AssertValid` -Memberfunktion des Objekts als Argument übergeben.  
  
 In der Releaseversion von MFC `ASSERT_VALID` wird keine Aktion ausgeführt. In der Debugversion den Zeiger überprüft, überprüft **NULL**, und ruft die eigenen `AssertValid` Memberfunktionen. Wenn einer dieser tests fehlschlägt, wird eine Warnung angezeigt, auf die gleiche Weise wie [ASSERT](#assert).  
  
> [!NOTE]
>  Diese Funktion steht nur in der Debugversion von MFC.  
  
 Weitere Informationen und Beispiele finden Sie unter [Debuggen MFC-Anwendung](/visualstudio/debugger/mfc-debugging-techniques).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample Nr.&19;](../../mfc/codesnippet/cpp/diagnostic-services_5.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h

##  <a name="a-namedebugnewa--debugnew"></a><a name="debug_new"></a>DEBUG_NEW  
 Suchen von Arbeitsspeicherverlusten unterstützt.  
  
```   
#define  new DEBUG_NEW   
```  
  
### <a name="remarks"></a>Hinweise  
 Können `DEBUG_NEW` überall in Ihrer Anwendung, die Sie, in der Regel verwenden möchten die **neue** Operator zum Heap reservieren.  
  
 Im Debugmodus (wenn der **_DEBUG** Symbol definiert ist), `DEBUG_NEW` werden Nachverfolgen von den Dateinamen und Zeilennummern jedes von ihm reservierten Objekts. Wenn Sie verwenden die [CMemoryState](cmemorystate-structure.md#dumpallobjectssince) Member-Funktion, jedes Objekt mit zugeordneten `DEBUG_NEW` wird angezeigt mit der Dateiname und Zeilennummer, in der es reserviert wurde.  
  
 Mit `DEBUG_NEW`, legen Sie die folgende Direktive in den Quelldateien:  
  
 [!code-cpp[NVC_MFCCObjectSample&14;](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 Nach dem Einfügen von dieser Richtlinie wird der Präprozessor einfügen `DEBUG_NEW` verwenden Sie wo **neue**, MFC übernimmt den Rest. Wenn Sie eine Releaseversion des Programms kompilieren `DEBUG_NEW` aufgelöst wird, um eine einfache **neue** Vorgang und den Dateinamen und Zeilennummern werden nicht generiert.  
  
> [!NOTE]
>  In früheren Versionen von MFC (4.1 und früher) mussten Sie setzen die `#define` Anweisung, nachdem alle Anweisungen, die aufgerufen der `IMPLEMENT_DYNCREATE` oder `IMPLEMENT_SERIAL` Makros. Dies ist nicht mehr erforderlich.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h

##  <a name="a-namedebugonlya--debugonly"></a><a name="debug_only"></a>DEBUG_ONLY  
 Im Debugmodus (wenn der **_DEBUG** Symbol definiert ist), `DEBUG_ONLY` wertet das Argument.  
  
```   
DEBUG_ONLY(expression)   
```  
  
### <a name="remarks"></a>Hinweise  
 In einem Releasebuild **DEBUG_ONLY** Argument wird nicht ausgewertet. Dies ist hilfreich, wenn Sie über Code verfügen, die nur in Debug-Builds ausgeführt werden soll.  
  
 Die `DEBUG_ONLY` Makro entspricht umgebenden *Ausdruck* mit **#ifdef _DEBUG** und `#endif`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities&#32;](../../mfc/codesnippet/cpp/diagnostic-services_6.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h

##  <a name="a-nametracea--trace"></a><a name="trace"></a>TRACE  
 Sendet die angegebene Zeichenfolge an den Debugger von der aktuellen Anwendung.  
  
```   
TRACE(exp)  
TRACE(DWORD  category,  UINT  level, LPCSTR lpszFormat, ...)   
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [ATLTRACE2](http://msdn.microsoft.com/library/467ff555-e7a5-4f94-bdd9-50ee27ab9986) eine Beschreibung der **TRACE**. **TRACE** und `ATLTRACE2` weisen dasselbe Verhalten auf.  
  
 In der Debugversion von MFC sendet dieses Makro die angegebene Zeichenfolge an den Debugger von der aktuellen Anwendung. In einem Releasebuild kompiliert dieses Makro auf nothing (es ist überhaupt kein Code generiert).  
  
 Weitere Informationen finden Sie unter [Debuggen MFC-Anwendung](/visualstudio/debugger/mfc-debugging-techniques).  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h

##  <a name="a-nameverifya--verify"></a><a name="verify"></a>VERGEWISSERN SIE SICH  
 In der Debugversion von MFC wertet das Argument.  
  
```   
VERIFY(booleanExpression)   
```  
  
### <a name="parameters"></a>Parameter  
 `booleanExpression`  
 Gibt einen Ausdruck (einschließlich Zeiger), der einen Wert ungleich NULL oder 0 ergibt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Ergebnis 0 ist, wird das Makro druckt eine diagnosemeldung und hält das Programm an. Wenn die Bedingung einen Wert ungleich NULL ist, wird keine Aktion ausgeführt.  
  
 Die Diagnosemeldung hat die Form  
  
 `assertion failed in file <name> in line <num>`  
  
 wobei *Namen* ist der Name der Quelldatei und *Num* wird die Zeilennummer der Assertion ist, in der Quelldatei Fehler.  
  
 In der Releaseversion von MFC **überprüfen** wertet den Ausdruck jedoch nicht drucken oder unterbrechen Sie das Programm. Z. B. wenn der Ausdruck einen Funktionsaufruf ist, wird der Aufruf erfolgen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#198;](../../mfc/codesnippet/cpp/diagnostic-services_7.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h

##  <a name="a-namecdumpcontextinmfca--afxdump-cdumpcontext-in-mfc"></a><a name="cdumpcontext_in_mfc_"></a>AfxDump (CDumpContext in MFC)  
 Stellt grundlegende Objektdumps Funktion in Ihrer Anwendung bereit.  
  
```   
CDumpContext  afxDump;   
```  
  
### <a name="remarks"></a>Hinweise  
 `afxDump`ist ein vordefinierter [CDumpContext](../../mfc/reference/cdumpcontext-class.md) -Objekt, das Sie senden kann `CDumpContext` Informationen in das Ausgabefenster des Debuggers oder an ein Debug-Terminal. Geben Sie in der Regel `afxDump` als Parameter für `CObject::Dump`.  
  
 Unter Windows NT und allen Versionen von Windows `afxDump` Ausgabe wird an das Ausgabe-Debug-Fenster von Visual C++ gesendet, wenn Sie die Anwendung debuggen.  
  
 Diese Variable wird nur in der Debugversion von MFC definiert. Weitere Informationen zu `afxDump`, finden Sie unter [Debuggen MFC-Anwendung](/visualstudio/debugger/mfc-debugging-techniques).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities&23;](../../mfc/codesnippet/cpp/diagnostic-services_8.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h

##  <a name="a-nameafxmemdfa--afxmemdf"></a><a name="afxmemdf"></a>afxMemDF  
 Diese Variable wird über einen Debugger oder das Programm und ermöglicht es Ihnen, die Zuordnung Diagnose zu optimieren.  
  
```   
int  afxMemDF;  
```  
  
### <a name="remarks"></a>Hinweise  
 `afxMemDF`können die folgenden Werte gemäß der Enumeration `afxMemDF`:  
  
- **AllocMemDF** Debuggen Zuweisung (in Debugbibliothek Standardeinstellung) aktiviert.  
  
- **DelayFreeMemDF** Speicherfreigabe verzögert. Während das Programm einen Speicherblock frei, gibt die Zuweisung nicht, dass der Arbeitsspeicher des zugrunde liegenden Betriebssystems zurück. Dies führt Maximaler Arbeitsspeicher Programm Belastung.  
  
- **CheckAlwaysMemDF** Aufrufe `AfxCheckMemory` jedes Mal, wenn Arbeitsspeicher reserviert oder freigegeben wird. Dies verlangsamt sich erheblich auf speicherbelegungen und Aufhebungen aus.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities&#30;](../../mfc/codesnippet/cpp/diagnostic-services_9.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h

##  <a name="a-nameafxcheckerrora--afxcheckerror"></a><a name="afxcheckerror"></a>AfxCheckError  
 Diese Funktion prüft das übergebene **SCODE** um festzustellen, ob es sich um einen Fehler handelt.  
  
```   
void AFXAPI AfxCheckError(SCODE sc);
throw CMemoryException* 
throw COleException*  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn es sich um einen Fehler handelt, wird die Funktion eine Ausnahme auslöst. Wenn der übergebene `SCODE` ist **E_OUTOFMEMORY**, löst die Funktion einer [CMemoryException](../../mfc/reference/cmemoryexception-class.md) durch Aufrufen von [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception). Andernfalls löst die Funktion einer [COleException verfügt](../../mfc/reference/coleexception-class.md) durch Aufrufen von [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 Diese Funktion kann verwendet werden, um die Rückgabewerte für Aufrufe von OLE-Funktionen in Ihrer Anwendung zu überprüfen. Den Rückgabewert dieser Funktion in Ihrer Anwendung testen, können Sie auf Fehlerzustände mit einer minimalen Menge an Code ordnungsgemäß reagieren.  
  
> [!NOTE]
>  Diese Funktion hat die gleiche Auswirkung im Debugmodus und nicht-Debugbuilds.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&33;](../../mfc/codesnippet/cpp/diagnostic-services_10.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h

##  <a name="a-nameafxcheckmemorya--afxcheckmemory"></a><a name="afxcheckmemory"></a>AfxCheckMemory  
 Diese Funktion überprüft den freien Speicherpool und gibt Fehlermeldungen wie erforderlich.  
  
```   
BOOL  AfxCheckMemory(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn keine Speicherfehler; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Funktion keine beschädigten Speicher erkennt, wird nichts ausgegeben.  
  
 Alle Speicherblöcke, die derzeit auf dem Heap reserviert werden überprüft, einschließlich von **neue** aber nicht diejenigen, die durch direkte Aufrufe der zugrunde liegenden speicherzuordnungen, wie z. B. die `malloc` Funktion oder die **GlobalAlloc** Windows-Funktion. Wenn jeder Block gefunden wird, beschädigt zu sein, wird eine Meldung an die Ausgabe des Debuggers angezeigt.  
  
 Wenn Sie die Zeile einfügen  
  
 [!code-cpp[NVC_MFCCObjectSample&14;](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 in einem Programmmodul dann nachfolgende Aufrufe von `AfxCheckMemory` Anzeigen der Dateiname und Zeilennummer angegeben, in dem der Speicher belegt wurde.  
  
> [!NOTE]
>  Wenn das Modul eine oder mehrere Implementierungen von serialisierbaren Klassen enthält, muss die `#define` Zeile nach dem letzten `IMPLEMENT_SERIAL` Makro-Aufruf.  
  
 Diese Funktion funktioniert nur in der Debugversion von MFC.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample&#26;](../../mfc/codesnippet/cpp/diagnostic-services_11.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
 
##  <a name="a-namemfca--afxdump-mfc"></a><a name="mfc_"></a>AfxDump (MFC)  
 Rufen Sie diese Funktion im Debugger, um den Zustand eines Objekts während des Debuggens zu sichern.  
  
```   
void AfxDump(const CObject* pOb); 
```  
  
### <a name="parameters"></a>Parameter  
 `pOb`  
 Ein Zeiger auf ein Objekt einer Klasse abgeleitet `CObject`.  
  
### <a name="remarks"></a>Hinweise  
 **AfxDump** Ruft ein Objekt `Dump` -Memberfunktion und sendet die Informationen zum Speicherort, von angegeben dem `afxDump` Variable. **AfxDump** steht nur in der Debugversion von MFC.  
  
 Im Code sollte nicht aufrufen **AfxDump**, müssen jedoch stattdessen die `Dump` -Memberfunktion des entsprechenden Objekts.  
  
##  <a name="a-nameafxdumpstacka--afxdumpstack"></a><a name="afxdumpstack"></a>AfxDumpStack  
 Diese globale Funktion kann verwendet werden, um ein Bild des aktuellen Stapels zu generieren.  
  
```   
void AFXAPI AfxDumpStack(DWORD dwTarget = AFX_STACK_DUMP_TARGET_DEFAULT); 
```  
  
### <a name="parameters"></a>Parameter  
 *dwTarget*  
 Gibt das Ziel der Dump ausgegeben. Mögliche Werte, die mit dem bitweisen OR kombiniert werden können ( **|**)-Operator lauten wie folgt:  
  
- **AFX_STACK_DUMP_TARGET_TRACE** sendet die Ausgabe von der [TRACE](#trace) Makro. Die **TRACE** Makro generiert eine Ausgabe in Debugversionen nur; er generiert keine Ausgabe in Releasebuilds. Darüber hinaus **TRACE** zu anderen Zielen neben der Debugger umgeleitet werden können.  
  
- **AFX_STACK_DUMP_TARGET_DEFAULT** sendet dump Ausgabe an das Standardziel. Für einen Debugbuild Ausgabe wird an die **TRACE** Makro. In einem Releasebuild erfolgt die Ausgabe in die Zwischenablage.  
  
- **AFX_STACK_DUMP_TARGET_CLIPBOARD** sendet die Ausgabe in die Zwischenablage nur. Befindet sich die Daten in der Zwischenablage als nur-Text mit der **CF_TEXT** Format der Zwischenablage.  
  
- **AFX_STACK_DUMP_TARGET_BOTH** sendet die Ausgabe in die Zwischenablage und zu den **TRACE** Makro gleichzeitig.  
  
- **AFX_STACK_DUMP_TARGET_ODS** sendet die Ausgabe direkt an den Debugger durch die Win32-Funktion **OutputDebugString()**. Diese Option generiert Debuggerausgabe in Debug- und Releasebuilds, wenn ein Debugger an den Prozess angefügt ist. **AFX_STACK_DUMP_TARGET_ODS** den Debugger immer erreicht, (Wenn sie angefügt ist) und kann nicht umgeleitet werden.  
  
### <a name="remarks"></a>Hinweise  
 Das folgende Beispiel gibt eine einzelne Zeile durch den Aufruf generierte Ausgabe `AfxDumpStack` aus einem Ereignishandler der Schaltfläche in einem MFC-Dialogfeld Anwendung:  
  
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
  
 Jede Zeile in der obigen Ausgabe gibt die Adresse des letzten Funktionsaufrufs, der vollständige Name des Moduls, der Aufruf der Funktion und der Funktionsprototyp Namens enthält. Wenn der Funktionsaufruf auf dem Stapel nicht an die genaue Adresse der Funktion geschieht, wird ein Offset von Bytes angezeigt.  
  
 In der folgenden Tabelle werden beispielsweise die erste Zeile der Ausgabe oben beschrieben:  
  
|Ausgabe|Beschreibung|  
|------------|-----------------|  
|`00427D55:`|Die Absenderadresse des letzten Funktionsaufrufs.|  
|`DUMP2\DEBUG\DUMP2.EXE!`|Der vollständige Name des Moduls, das den Funktionsaufruf enthält.|  
|`void AfxDumpStack(unsigned long)`|Der Funktionsprototyp aufgerufen.|  
|`+ 181 bytes`|Der Offset in Bytes, die von der Adresse der Funktionsprototyp (in diesem Fall `void AfxDumpStack(unsigned long)`) an die Rücksendeadresse (in diesem Fall `00427D55`).|  
  
 `AfxDumpStack`steht in Debug- und aufgeführt Versionen der MFC-Bibliotheken. die Funktion ist auch, wenn die ausführbare Datei in einer gemeinsam genutzten DLL MFC verwendet jedoch immer statisch verknüpft. Die Funktion ist in gemeinsam genutzte Bibliothek Implementierungen in der MFCS42 gefunden. LIB-Bibliothek (und seine Varianten).  
  
 Diese Funktion wurde erfolgreich zu verwenden:  
  
-   Die Datei IMAGEHLP. DLL muss auf Ihrem Pfad befinden. Wenn Sie nicht über diese DLL-Datei verfügen, wird die Funktion eine Fehlermeldung angezeigt. Finden Sie unter [Bild Hilfebibliothek](http://msdn.microsoft.com/library/windows/desktop/ms680321) Informationen zu den festgelegten von IMAGEHLP bereitgestellt.  
  
-   Die Module, die über Frames auf dem Stapel müssen Debuginformationen einschließen. Wenn sie keine Debuginformationen enthalten, generiert die Funktion immer noch eine stapelüberwachung, aber die Trace weniger detailliert.  
### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="a-nameafxenablememoryleakdumpa--afxenablememoryleakdump"></a><a name="afxenablememoryleakdump"></a>AfxEnableMemoryLeakDump  
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
 Wenn eine Anwendung die MFC-Bibliothek entlädt, führt die MFC-Bibliothek eine Überprüfung auf Speicherverluste aus. An diesem Punkt werden alle Speicherverluste gemeldet, für den Benutzer über die **Debuggen** Fenster [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)].  
  
 Wenn Ihre Anwendung eine andere Bibliothek vor der MFC-Bibliothek lädt, werden einige Speicherbelegungen in dieser Bibliothek fälschlicherweise als Arbeitsspeicherverluste gemeldet. Wegen Arbeitsspeicherverlusten, die eigentlich keine sind, wird Ihre Anwendung möglicherweise langsam beendet, da die MFC-Bibliothek die Speicherverluste meldet. Verwenden Sie in diesem Fall `AfxEnableMemoryLeakDump` , um das Speicherabbild des Arbeitsspeicherverlusts zu deaktivieren.  
  
> [!NOTE]
>  Wenn Sie diese Methode verwenden, um das Speicherabbild des Arbeitsspeicherverlusts deaktivieren, erhalten Sie keine Berichte über tatsächliche Arbeitsspeicherverluste in Ihrer Anwendung. Sie sollten diese Methode nur verwenden, wenn Sie sicher sind, dass der Bericht über die Arbeitsspeicherverluste falsche Meldungen enthält.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="a-nameafxenablememorytrackinga--afxenablememorytracking"></a><a name="afxenablememorytracking"></a>AfxEnableMemoryTracking  
 Diagnose speicherüberwachung ist normalerweise in der Debugversion des MFC-aktiviert.  
  
```   
BOOL AfxEnableMemoryTracking(BOOL bTrack); 
```  
  
### <a name="parameters"></a>Parameter  
 *bTrack*  
 Wenn dieser Wert auf **TRUE** schaltet Arbeitsspeicher überwachen; **FALSE** deaktiviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherige Einstellung des Flags Tracking zu aktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion auf die um Überwachung auf Abschnitte des Codes zu deaktivieren, die Sie kennen Blöcke ordnungsgemäß zugeordnet werden.  
  
 Weitere Informationen zu `AfxEnableMemoryTracking`, finden Sie unter [Debuggen MFC-Anwendung](/visualstudio/debugger/mfc-debugging-techniques).  
  
> [!NOTE]
>  Diese Funktion funktioniert nur in der Debugversion von MFC.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities&#24;](../../mfc/codesnippet/cpp/diagnostic-services_12.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="a-nameafxismemoryblocka--afxismemoryblock"></a><a name="afxismemoryblock"></a>AfxIsMemoryBlock  
 Testet eine Speicheradresse, um sicherzustellen, dass dar, einen derzeit aktiven Speicherblock, der von der Diagnose Version von reserviert wurde **neue**.  
  
```   
BOOL AfxIsMemoryBlock(
    const void* p,  
    UINT nBytes,  
    LONG* plRequestNumber = NULL); 
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Verweist auf den Speicherblock, der getestet werden soll.  
  
 `nBytes`  
 Enthält die Länge des Speicherblocks in Bytes.  
  
 `plRequestNumber`  
 Verweist auf eine **lang** ganze Zahl, die wird der Speicherblock Zuordnung Sequenznummer ausgefüllt werden, oder&0;, wenn er nicht gerade aktiven Speicherblock darstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Speicherblock derzeit belegt ist und die Länge korrekt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Außerdem überprüft die angegebene Größe für die ursprüngliche zugeordnete Größe. Wenn die Funktion einen Wert ungleich NULL zurückgibt, wird die Sequenznummer für die Zuordnung zurückgegeben `plRequestNumber`. Diese Zahl stellt die Reihenfolge, in dem der Block, im Vergleich zu allen anderen belegt wurde **neue** Zuordnungen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities&#27;](../../mfc/codesnippet/cpp/diagnostic-services_13.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="a-nameafxisvalidaddressa--afxisvalidaddress"></a><a name="afxisvalidaddress"></a>AfxIsValidAddress  
 Prüft jede beliebige Speicheradresse, um sicherzustellen, dass sie vollständig im Speicher für die Anwendung enthalten ist.  
  
```   
BOOL AfxIsValidAddress(
    const void* lp,  
    UINT nBytes,  
    BOOL bReadWrite = TRUE); 
```  
  
### <a name="parameters"></a>Parameter  
 `lp`  
 Verweist auf die Speicheradresse getestet werden soll.  
  
 `nBytes`  
 Enthält die Anzahl der Bytes im Speicher getestet werden soll.  
  
 *bReadWrite*  
 Gibt an, ob der Speicher sowohl zum Lesen und Schreiben ( **TRUE**) oder nur lesen ( **FALSE**).  
  
### <a name="return-value"></a>Rückgabewert  
 In Debugbuilds ist ungleich NULL, wenn der angegebene Speicher-block vollständig im Speicher für die Anwendung enthalten; andernfalls 0.  
  
 In nicht-Debugbuilds einen Wert ungleich NULL `lp` nicht NULL ist, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Adresse ist nicht eingeschränkt, Blöcke, die von **neue**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities&#28;](../../mfc/codesnippet/cpp/diagnostic-services_14.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="a-nameafxisvalidstringa--afxisvalidstring"></a><a name="afxisvalidstring"></a>AfxIsValidString  
 Verwenden Sie diese Funktion, um zu bestimmen, ob ein Zeiger auf eine Zeichenfolge gültig ist.  
  
```   
BOOL  AfxIsValidString(
    LPCSTR lpsz,  
    int nLength = -1); 
```  
  
### <a name="parameters"></a>Parameter  
 `lpsz`  
 Der Zeiger auf testen.  
  
 `nLength`  
 Gibt die Länge der Zeichenfolge, die getestet werden, in Bytes. Ein Wert von Â €"1 bedeutet, dass die Zeichenfolge Null-terminiert.  
  
### <a name="return-value"></a>Rückgabewert  
 In Debugbuilds ungleich NULL, wenn der angegebene Zeiger auf eine Zeichenfolge mit der angegebenen Größe verweist; andernfalls 0.  
  
 In nicht-Debugbuilds einen Wert ungleich NULL `lpsz` nicht NULL ist, andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities&#29;](../../mfc/codesnippet/cpp/diagnostic-services_15.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="a-nameafxsetallochooka--afxsetallochook"></a><a name="afxsetallochook"></a>AfxSetAllocHook  
 Legt einen Hook ein, mit dem Aufruf der angegebenen Funktion kann, bevor jeden Speicherblock zugeordnet ist.  
  
```   
AFX_ALLOC_HOOK AfxSetAllocHook(AFX_ALLOC_HOOK pfnAllocHook); 
```  
  
### <a name="parameters"></a>Parameter  
 *pfnAllocHook*  
 Gibt den Namen der aufzurufenden Funktion. Finden Sie die Hinweise für den Prototyp einer Zuordnung-Funktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Zuweisung zugelassen werden soll; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Microsoft Foundation Class Library Debug-Speicherreservierungsfunktion kann, dass der Benutzer zum Belegen von Speicher zu überwachen und zu steuern, ob die Zuordnung zulässig ist eine benutzerdefinierte Hookfunktion aufrufen. Hookfunktionen lauten wie folgt einen Prototyp haben:  
  
 **BOOL AFXAPI AllocHook( size_t** `nSize`**, BOOL** `bObject`**, LONG** `lRequestNumber` **);**  
  
 `nSize`  
 Die Größe der vorgeschlagenen speicherbelegung.  
  
 `bObject`  
 **True,** ist die Zuordnung für einen `CObject`-abgeleitetes Objekt andernfalls **FALSE**.  
  
 `lRequestNumber`  
 Sequenznummer der speicherbelegung.  
  
 Beachten Sie, dass die **AFXAPI** -Aufrufkonvention gibt an, dass der aufgerufene die Parameter aus dem Stapel entfernt werden muss.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="a-nameafxdoforallclassesa--afxdoforallclasses"></a><a name="afxdoforallclasses"></a>AfxDoForAllClasses  
 Ruft die angegebene Iteration-Funktion für alle serialisierbaren `CObject`-abgeleiteten Klassen im Speicherbereich für die Anwendung.  
  
```   
void  
AFXAPI AfxDoForAllClasses(
    void (* pfn)(const CRuntimeClass* pClass, void* pContext),  
    void* pContext); 
```  
  
### <a name="parameters"></a>Parameter  
 `pfn`  
 Zeigt auf eine Iteration-Funktion für jede Klasse aufgerufen werden. Die Argumente der Funktion sind ein Zeiger auf ein `CRuntimeClass` -Objekt und einen void-Zeiger auf zusätzliche Daten, die der Aufrufer der Funktion bereitstellt.  
  
 `pContext`  
 Verweist auf die optionalen Daten, die der Aufrufer der Funktion Iteration bereitgestellt werden kann. This-Zeiger kann **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Serialisierbare `CObject`-abgeleiteten Klassen sind über abgeleitete Klassen den `DECLARE_SERIAL` Makro. Der Zeiger, der an `AfxDoForAllClasses` in `pContext` wird jedes Mal aufgerufen wird an die angegebene Iteration-Funktion übergeben.  
  
> [!NOTE]
>  Diese Funktion funktioniert nur in der Debugversion von MFC.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#113;](../../mfc/codesnippet/cpp/diagnostic-services_16.cpp)]  
  
 [!code-cpp[NVC_MFCCollections&#114;](../../mfc/codesnippet/cpp/diagnostic-services_17.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="a-nameafxdoforallobjectsa--afxdoforallobjects"></a><a name="afxdoforallobjects"></a>AfxDoForAllObjects  
 Führt die angegebene Iteration-Funktion für alle Objekte aus abgeleitete `CObject` mit zugeordnet wurde **neue**.  
  
```   
void AfxDoForAllObjects(
    void (* pfn)(CObject* pObject, void* pContext),  
    void* pContext); 
```  
  
### <a name="parameters"></a>Parameter  
 `pfn`  
 Zeigt auf eine Iteration-Funktion, die für jedes Objekt ausgeführt. Die Argumente der Funktion sind ein Zeiger auf eine `CObject` und einen void-Zeiger auf zusätzliche Daten, die der Aufrufer der Funktion bereitstellt.  
  
 `pContext`  
 Verweist auf die optionalen Daten, die der Aufrufer der Funktion Iteration bereitgestellt werden kann. This-Zeiger kann **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Stapel, globale oder eingebettete Objekte werden nicht aufgezählt. Der Zeiger übergeben wird, um `AfxDoForAllObjects` in `pContext` wird jedes Mal aufgerufen wird an die angegebene Iteration-Funktion übergeben.  
  
> [!NOTE]
>  Diese Funktion funktioniert nur in der Debugversion von MFC.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#115;](../../mfc/codesnippet/cpp/diagnostic-services_18.cpp)]  
  
 [!code-cpp[NVC_MFCCollections Nr.&116;](../../mfc/codesnippet/cpp/diagnostic-services_19.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
