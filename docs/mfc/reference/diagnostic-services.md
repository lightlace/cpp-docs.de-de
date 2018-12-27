---
title: Diagnosedienste
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros
helpviewer_keywords:
- diagnosi [MFC]s, diagnostic services
- diagnostic macros [MFC], list of general MFC
- services [MFC], diagnostic
- MFC, diagnostic services
- general diagnostic functions and variables [MFC]
- diagnostics [MFC], diagnostic functions and variables
- diagnostics [MFC], list of general MFC
- diagnosis [MFC], diagnostic functions and variables
- diagnosis [MFC], list of general MFC
- general diagnostic macros in MFC
- diagnostic macros [MFC]
- diagnostic services [MFC]
- object diagnostic functions in MFC
- diagnostics [MFC], diagnostic services
- diagnostic functions and variables [MFC]
ms.assetid: 8d78454f-9fae-49c2-88c9-d3fabd5393e8
ms.openlocfilehash: dbb243453b6d869082a4232b12b27f5510d84aa5
ms.sourcegitcommit: 53f75afaf3c0b3ed481c5503357ed2b7b87aac6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2018
ms.locfileid: "53657629"
---
# <a name="diagnostic-services"></a>Diagnosedienste

Die Microsoft Foundation Class-Bibliothek bietet viele Diagnosedienste, die das Debuggen von Programmen erleichtern. Zu diesen Diagnosediensten zählen Makros und globale Funktionen, die Ihnen das Nachverfolgen der Speicherzuweisungen von Programmen, das Sichern des Inhalts von Objekten zur Laufzeit und das Ausgeben von Debugmeldungen zur Laufzeit ermöglichen. Die Makros und globalen Funktionen für Diagnosedienste sind in folgende Kategorien gruppiert:

- Allgemeine Diagnosemakros

- Allgemeine Diagnosefunktionen und -Variablen

- Objektdiagnosefunktionen

Diese Makros und Funktionen stehen in den Debug- und den endgültigen Produktversionen von MFC für alle von `CObject` abgeleiteten Klassen zur Verfügung. Allerdings nichts Unternehmen alles außer DEBUG_NEW und stellen Sie sicher in der endgültigen Produktversion.

In der Debugbibliothek stehen alle zugewiesenen Speicherblöcke in aus einer Reihe von "Wächterbytes" bestehenden Klammern. Wenn diese Bytes durch einen fehlerhaften Schreibzugriff auf den Speicher gestört werden, können die Diagnoseroutinen ein Speicherproblem melden. Wenn Sie diese Zeile:

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

in Ihre Implementierungsdatei einschließen, werden für jeden Aufruf von **new** der Dateiname und die Zeilennummer gespeichert, für die die Speicherzuweisung erfolgt ist. Die Funktion [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince) zeigt diese Zusatzinformationen an, was Ihnen das Erkennen von Speicherverlusten ermöglicht. Weitere Informationen zur Diagnoseausgabe finden Sie auch bei der Klasse [CDumpContext](../../mfc/reference/cdumpcontext-class.md) .

Darüber hinaus unterstützt die C-Laufzeitbibliothek auch eine Reihe von Diagnosefunktionen, die Sie zum Debuggen von Anwendungen verwenden können. Weitere Informationen finden Sie unter [Debugroutinen](../../c-runtime-library/debug-routines.md) in der Referenz zur Laufzeitbibliothek.

### <a name="mfc-general-diagnostic-macros"></a>Allgemeine MFC-Diagnosemakros

|||
|-|-|
|[ASSERT](#assert)|Gibt eine Meldung, und bricht dann das Programm ab, wenn der angegebene Ausdruck in der Debugversion der Bibliothek "false" ausgewertet wird.|
|[ASSERT_KINDOF](#assert_kindof)|Prüft, ob ein Objekt ein Objekt der angegebenen Klasse oder einer aus der angegebenen Klasse abgeleiteten Klasse ist.|
|[ASSERT_VALID](#assert_valid)|Prüft die interne Gültigkeit eines Objekts durch Aufrufen seiner `AssertValid` -Memberfunktion; normalerweise durch `CObject`außer Kraft gesetzt.|
|[DEBUG_NEW](#debug_new)|Gibt einen Dateinamen und eine Zeilennummer für alle Objektzuweisungen im Debugmodus an, um die Suche nach Speicherverlusten zu unterstützen.|
|[DEBUG_ONLY](#debug_only)|ASSERT ähnelt prüft jedoch nicht den Wert des Ausdrucks ist; ist nützlich für Code, der nur im Debugmodus ausgeführt werden soll.|
|[Stellen Sie sicher und ENSURE_VALID](#ensure)|Verwenden Sie, um Daten auf Richtigkeit zu überprüfen.|
|[THIS_FILE](#this_file)|Wird erweitert, um den Namen der Datei, die kompiliert wird.|
|[TRACE](#trace)|Stellt eine `printf`-ähnliche Funktionalität in der Debugversion der Bibliothek zur Verfügung.|
|[VERIFY](#verify)|Ähnlich wie bei ASSERT wertet jedoch den Ausdruck in der endgültigen Produktversion der Bibliothek als auch in der Debugversion aus.|

### <a name="mfc-general-diagnostic-variables-and-functions"></a>Allgemeine MFC-Diagnosevariablen und -Funktionen

|||
|-|-|
|[afxDump](#afxdump)|Globale Variable, die [CDumpContext](../../mfc/reference/cdumpcontext-class.md) -Informationen an das Debuggerausgabefenster oder das Debugterminal sendet.|
|[afxMemDF](#afxmemdf)|Globale Variable, die das Verhalten der Debugspeicherzuweisung steuert.|
|[AfxCheckError](#afxcheckerror)|Globale Variable, die zum Testen der übergebenen SCODE, um festzustellen, ob es ein Fehler auftritt und löst den entsprechenden Fehler aus, wenn dies der Fall ist, verwendet werden.|
|[AfxCheckMemory](#afxcheckmemory)|Überprüft die Integrität des gesamten derzeit zugewiesenen Speichers.|
|[AfxDebugBreak](#afxdebugbreak)|Bewirkt, dass eine Unterbrechung bei der Ausführung.|
|[AfxDump](#cdumpcontext_in_mfc)|Sichert bei einem Aufruf im Debugger den Status eines Objekts während des Debuggens.|
|[AfxDump](#afxdump)|Interne Funktion, der den Zustand eines Objekts während des Debuggens sichert.|
|[AfxDumpStack](#afxdumpstack)|Generiert ein Image des aktuellen Stapels. Diese Funktion wird immer statisch gelinkt.|
|[AfxEnableMemoryLeakDump](#afxenablememoryleakdump)|Ermöglicht das Sichern von Speicherverlusten.|
|[AfxEnableMemoryTracking](#afxenablememorytracking)|Aktiviert und deaktiviert die Arbeitsspeicher-Nachverfolgung.|
|[AfxIsMemoryBlock](#afxismemoryblock)|Überprüft, ob ein Speicherblock ordnungsgemäß zugewiesen wurde.|
|[AfxIsValidAddress](#afxisvalidaddress)|Überprüft, ob ein Speicheradressbereich innerhalb der Grenzen des Programms liegt.|
|[AfxIsValidString](#afxisvalidstring)|Bestimmt, ob ein Zeiger auf eine Zeichenfolge gültig ist.|
|[AfxSetAllocHook](#afxsetallochook)|Ermöglicht das Aufrufen einer Funktion für jede Speicherzuweisung.|

### <a name="mfc-object-diagnostic-functions"></a>MFC-Objektdiagnosefunktionen

|||
|-|-|
|[AfxDoForAllClasses](#afxdoforallclasses)|Führt eine angegebene Funktion für alle von `CObject`abgeleiteten Klassen aus, die Typprüfung zur Laufzeit unterstützen.|
|[AfxDoForAllObjects](#afxdoforallobjects)|Führt eine angegebene Funktion für alle von `CObject`abgeleiteten Objekte aus, die mithilfe von **new**zugewiesen wurden.|

### <a name="mfc-compilation-macros"></a>Kompilierung von MFC-Makros

|||
|-|-|
|[_AFX_SECURE_NO_WARNINGS](#afx_secure_no_warnings)|Unterdrückt die Compiler-Warnungen für die Verwendung von veralteten MFC-Funktionen.|

## <a name="afx_secure_no_warnings"></a> _AFX_SECURE_NO_WARNINGS

Unterdrückt die Compiler-Warnungen für die Verwendung von veralteten MFC-Funktionen.

### <a name="syntax"></a>Syntax

```
_AFX_SECURE_NO_WARNINGS
```

### <a name="example"></a>Beispiel

In diesem Codebeispiel würde eine compilerwarnung, wenn _AFX_SECURE_NO_WARNINGS nicht definiert wurden.

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

## <a name="afxdebugbreak"></a> AfxDebugBreak

Mit dieser Funktion können dazu führen, dass eine Unterbrechung (an der Position des Aufrufs von `AfxDebugBreak`) bei der Ausführung der Debugversion der MFC-Anwendung.

### <a name="syntax"></a>Syntax

```
void AfxDebugBreak( );
```

### <a name="remarks"></a>Hinweise

`AfxDebugBreak` wirkt sich nicht im Release-Versionen von MFC-Anwendung und sollte entfernt werden. Diese Funktion sollte nur in MFC-Anwendungen verwendet werden. Verwenden Sie die Win32-API-Version, `DebugBreak`, um eine Unterbrechung in MFC-fremden Anwendungen verursachen.

### <a name="requirements"></a>Anforderungen

**Header:** afxver_.h

##  <a name="assert"></a>  ASSERT

Wertet das Argument an.

```
ASSERT(booleanExpression)
```

### <a name="parameters"></a>Parameter

*boolescher Ausdruck*<br/>
Gibt einen Ausdruck (einschließlich Zeigerwerte), der ungleich NULL oder 0 ergibt.

### <a name="remarks"></a>Hinweise

Wenn das Ergebnis 0 ist, wird das Makro gibt eine diagnosemeldung und bricht das Programm ab. Wenn die Bedingung ungleich NULL ist, tut sie nichts.

Die Diagnosemeldung hat die Form

`assertion failed in file <name> in line <num>`

wo *Namen* ist der Name der Quelldatei, und *Num* die Zeilennummer der Assertion, die nicht in der Quelldatei.

In der Releaseversion von MFC Assert-Anweisung wird den Ausdruck nicht ausgewertet, und wird daher nicht das Programm unterbrochen. Wenn unabhängig von der Umgebung der Ausdruck ausgewertet werden muss, verwenden Sie anstelle von ASSERT das VERIFY-Makro.

> [!NOTE]
>  Diese Funktion ist nur in der Debugversion des MFC-verfügbar.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#44](../../mfc/codesnippet/cpp/diagnostic-services_2.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="assert_kindof"></a>  ASSERT_KINDOF

Dieses Makro wird bestätigt, dass das Objekt, auf ein Objekt der angegebenen Klasse oder ein Objekt einer Klasse sich aus der angegebenen Klasse ergibt.

```
ASSERT_KINDOF(classname, pobject)
```

### <a name="parameters"></a>Parameter

*classname*<br/>
Der Name des eine `CObject`-abgeleitete Klasse.

*pObject*<br/>
Ein Zeiger auf ein Objekt der Klasse.

### <a name="remarks"></a>Hinweise

Die *Pobject* Parameter muss ein Zeiger auf ein Objekt und kann **const**. Das Objekt verweist und die Klasse muss unterstützen `CObject` Laufzeit Klasseninformationen. Als Beispiel, um sicherzustellen, dass `pDocument` ist ein Zeiger auf ein Objekt der `CMyDoc` Klasse oder eines der dessen Derivate, Sie können code:

[!code-cpp[NVC_MFCDocView#194](../../mfc/codesnippet/cpp/diagnostic-services_3.cpp)]

Mithilfe der `ASSERT_KINDOF` Makro ist identisch mit der Codierung:

[!code-cpp[NVC_MFCDocView#195](../../mfc/codesnippet/cpp/diagnostic-services_4.cpp)]

Diese Funktion funktioniert nur für Klassen, die mit dem [DECLARE_DYNAMIC] (Run-Time-Objekt-Modell-services.md #Declare_dynamic oder [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) Makro.

> [!NOTE]
>  Diese Funktion ist nur in der Debugversion des MFC-verfügbar.

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="assert_valid"></a>  ASSERT_VALID

So testen Sie Ihre Annahmen über die Gültigkeit des internen Zustands eines Objekts verwenden.

```
ASSERT_VALID(pObject)
```

### <a name="parameters"></a>Parameter

*pObject*<br/>
Gibt ein Objekt einer Klasse abgeleitet `CObject` , die eine überschreibende Version der hat die `AssertValid` Member-Funktion.

### <a name="remarks"></a>Hinweise

ASSERT_VALID-Aufrufe der `AssertValid` -Memberfunktion des Objekts als Argument übergeben.

In der Releaseversion von MFC nichts ASSERT_VALID. In der Debugversion des Zeigers überprüft, für NULL überprüft und ruft das Objekt auf der eigenen `AssertValid` Memberfunktionen. Wenn eines dieser tests fehlschlägt, wird eine Warnmeldung angezeigt, auf die gleiche Weise wie [ASSERT](#assert).

> [!NOTE]
>  Diese Funktion ist nur in der Debugversion des MFC-verfügbar.

Weitere Informationen und Beispiele finden Sie unter [MFC-Anwendungen Debuggen](/visualstudio/debugger/mfc-debugging-techniques).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCObjectSample#19](../../mfc/codesnippet/cpp/diagnostic-services_5.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="debug_new"></a>  DEBUG_NEW

Suchen von Arbeitsspeicherverlusten unterstützt.

```
#define  new DEBUG_NEW
```

### <a name="remarks"></a>Hinweise

Können Sie DEBUG_NEW überall in Ihrem Programm, mit denen Sie normalerweise würde der **neue** Operator, um die Heap-Speicher zu belegen.

Im Debugmodus (wenn die **_DEBUG** Symbol definiert ist), DEBUG_NEW werden Nachverfolgen von den Dateinamen und Zeilennummern jedes von ihm reservierten Objekts. Klicken Sie dann bei Verwendung der [CMemoryState](cmemorystate-structure.md#dumpallobjectssince) Member-Funktion, jedes mit DEBUG_NEW zugeordnete Objekt wird angezeigt mit der Dateiname und Zeilennummer, in denen es reserviert wurde.

Um DEBUG_NEW zu verwenden, fügen Sie die folgende Anweisung in Ihre Quelldateien:

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

Nach dem Einfügen von dieser Richtlinie fügt der Präprozessor DEBUG_NEW an denen Sie verwendet **neue**, und MFC übernimmt den Rest. Wenn Sie eine Releaseversion des Programms kompilieren, DEBUG_NEW aufgelöst wird, um eine einfache **neue** Vorgang und den Dateinamen und Zeilennummern werden nicht generiert.

> [!NOTE]
>  In früheren Versionen von MFC (4.1 und früher) mussten Sie fügen die `#define` Anweisung nach der alle Anweisungen, die die Makros IMPLEMENT_DYNCREATE oder IMPLEMENT_SERIAL aufgerufen. Dies ist nicht mehr erforderlich.

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="debug_only"></a>  DEBUG_ONLY

Im Debugmodus (wenn die **_DEBUG** Symbol definiert ist), DEBUG_ONLY wertet das Argument.

```
DEBUG_ONLY(expression)
```

### <a name="remarks"></a>Hinweise

In einem Releasebuild wird DEBUG_ONLY nicht das Argument ausgewertet. Dies ist nützlich, wenn Sie über Code verfügen, die nur in Debug-Builds ausgeführt werden soll.

Die DEBUG_ONLY-Makro ist gleichbedeutend mit umgebenden *Ausdruck* mit `#ifdef _DEBUG` und `#endif`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#32](../../mfc/codesnippet/cpp/diagnostic-services_6.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

### <a name="ensure"></a>  Stellen Sie sicher und ENSURE_VALID

Verwenden Sie, um Daten auf Richtigkeit zu überprüfen.

### <a name="syntax"></a>Syntax

```
ENSURE(  booleanExpression )
ENSURE_VALID( booleanExpression  )
```

### <a name="parameters"></a>Parameter

*boolescher Ausdruck*<br/>
Gibt einen booleschen Ausdruck getestet werden.

### <a name="remarks"></a>Hinweise

Der Zweck dieser Makros ist, um die Validierung von Parametern zu verbessern. Die Makros zu verhindern, dass die weitere Verarbeitung der falsche Parameter in Ihrem Code. Im Gegensatz zu der ASSERT-Makros Ausnahme die Makros, die sicherstellen, dass eine neben der Erstellung einer Assertion.

Die Makros, die Verhalten auf zwei Arten entsprechend der Projektkonfiguration. Die Makros ASSERT aufrufen und dann eine Ausnahme auslöst, wenn die Assertion fehlschlägt. Daher (d. h. _DEBUG definiert ist) führen in Debugkonfigurationen die Makros, die eine Assertion und die Ausnahme beim in Version Konfigurationen für das Exportieren von Makros nur die Ausnahme, die (ASSERT wird nicht den Ausdruck in Releasekonfigurationen ausgewertet).

Das Makro wird das Makro stellen Sie sicher ENSURE_ARG fungiert.

ENSURE_VALID Ruft das ASSERT_VALID-Makro (die Auswirkungen nur in Debugbuilds aufweist). ENSURE_VALID ist außerdem eine Ausnahme ausgelöst, wenn der Zeiger NULL ist. Der NULL-Test wird in sowohl Debug- und Releasekonfigurationen ausgeführt.

Wenn einer dieser Tests fehlschlägt, wird eine Warnmeldung in die gleiche Weise wie ASSERT angezeigt. Das Makro löst eine Ausnahme für ungültiges Argument aus, bei Bedarf.
### <a name="requirements"></a>Anforderungen

**Header:** afx.h

### <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](mfc-macros-and-globals.md)<br/>
[VERIFY](#verify)<br/>
[ATLENSURE](#altensure)

## <a name="this_file"></a> THIS_FILE

Wird erweitert, um den Namen der Datei, die kompiliert wird.

### <a name="syntax"></a>Syntax

```
THIS_FILE
```

### <a name="remarks"></a>Hinweise

Die Informationen werden durch die Assert-Anweisung, und überprüfen Sie die Makros verwendet. Platzieren Sie die Anwendungs-Assistenten und Code-Assistenten das Makro in Quellcodedateien, die sie erstellen.

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

[Makros und globale Variablen](mfc-macros-and-globals.md)<br/>
[ASSERT](#assert)<br/>
[VERIFY](#verify)

##  <a name="trace"></a>  TRACE

Sendet die angegebene Zeichenfolge an den Debugger von der aktuellen Anwendung.

```
TRACE(exp)
TRACE(DWORD  category,  UINT  level, LPCSTR lpszFormat, ...)
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [ATLTRACE2](../../atl/reference/debugging-and-error-reporting-macros.md#atltrace2) eine Beschreibung der ABLAUFVERFOLGUNG. ABLAUFVERFOLGUNG und ATLTRACE2 weisen das gleiche Verhalten auf.

In der Debugversion von MFC sendet dieses Makro die angegebene Zeichenfolge an den Debugger von der aktuellen Anwendung. In einem Releasebuild kompiliert dieses Makro auf nichts verweist (es ist gar kein Code generiert).

Weitere Informationen finden Sie unter [MFC-Anwendungen Debuggen](/visualstudio/debugger/mfc-debugging-techniques).

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="verify"></a>  VERIFY

In der Debugversion von MFC wertet das Argument.

```
VERIFY(booleanExpression)
```

### <a name="parameters"></a>Parameter

*boolescher Ausdruck*<br/>
Gibt einen Ausdruck (einschließlich Zeigerwerte), der ungleich NULL oder 0 ergibt.

### <a name="remarks"></a>Hinweise

Wenn das Ergebnis 0 ist, wird das Makro gibt eine diagnosemeldung und hält das Programm an. Wenn die Bedingung ungleich NULL ist, tut sie nichts.

Die Diagnosemeldung hat die Form

`assertion failed in file <name> in line <num>`

wo *Namen* ist der Name der Quelldatei und *Num* die Zeilennummer der Assertion, die nicht in der Quelldatei.

In der Releaseversion von MFC stellen Sie sicher, wertet den Ausdruck jedoch nicht drucken oder das Programm zu unterbrechen. Z. B. wenn der Ausdruck auf ein Funktionsaufruf ist, wird der Aufruf erfolgen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#198](../../mfc/codesnippet/cpp/diagnostic-services_7.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="cdumpcontext_in_mfc"></a>  AfxDump (CDumpContext in MFC)

Stellt grundlegende Objektdumps Funktion in Ihrer Anwendung bereit.

```
CDumpContext  afxDump;
```

### <a name="remarks"></a>Hinweise

`afxDump` ein vordefiniertes [CDumpContext](../../mfc/reference/cdumpcontext-class.md) -Objekt, das Sie senden kann `CDumpContext` -Informationen an das debuggerausgabefenster oder ein debugterminal. Geben Sie in der Regel `afxDump` als Parameter an `CObject::Dump`.

Unter Windows NT und allen Versionen von Windows `afxDump` Ausgabe wird an das Ausgabe-Debug-Fenster von Visual C++ gesendet, wenn Sie die Anwendung zu debuggen.

Diese Variable wird nur in der Debugversion von MFC definiert. Weitere Informationen zu `afxDump`, finden Sie unter [MFC-Anwendungen Debuggen](/visualstudio/debugger/mfc-debugging-techniques).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#23](../../mfc/codesnippet/cpp/diagnostic-services_8.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

## <a name="afxdump"></a> AfxDump (intern)

Interne Funktion, den MFC verwendet, um den Zustand eines Objekts während des Debuggens zu sichern.

### <a name="syntax"></a>Syntax

```
void AfxDump(const CObject* pOb);
```

### <a name="parameters"></a>Parameter

*Geschäftssitz*<br/>
Ein Zeiger auf ein Objekt einer Klasse abgeleitet `CObject`.

### <a name="remarks"></a>Hinweise

`AfxDump` Ruft ein Objekt des `Dump` Memberfunktion und sendet die Informationen zu dem Speicherort angegeben wird, durch die `afxDump` Variable. `AfxDump` ist nur in der Debugversion des MFC-verfügbar.

Programmcode sollte nicht aufrufen `AfxDump`, aber Sie sollten stattdessen aufrufen, die `Dump` -Memberfunktion des entsprechenden Objekts.

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

### <a name="see-also"></a>Siehe auch

[CObject::Dump](cobject-class.md#dump)

##  <a name="afxmemdf"></a>  afxMemDF

Diese Variable wird von einem Debugger oder Ihr Programm zugegriffen werden kann und ermöglicht es Ihnen Diagnose der speicherbelegung zu optimieren.

```
int  afxMemDF;
```

### <a name="remarks"></a>Hinweise

`afxMemDF` Lassen Sie die folgenden Werte gemäß der Enumeration `afxMemDF`:

- `allocMemDF` Aktiviert die debugging-Zuweisung (Standardeinstellung in Debugbibliothek).

- `delayFreeMemDF` Verzögerungen bei der Freigabe von Speicher. Während das Programm einen Speicherblock frei, gibt die Zuweisung nicht, dass der Speicher für das zugrunde liegende Betriebssystem zurück. Dies platziert die Belastung des maximalen Arbeitsspeichers für das Programm.

- `checkAlwaysMemDF` Aufrufe `AfxCheckMemory` jedes Mal, wenn Speicher belegt oder freigegeben ist. Dadurch wird bedeutend speicherbelegungen und Aufhebungen verlangsamen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#30](../../mfc/codesnippet/cpp/diagnostic-services_9.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxcheckerror"></a>  AfxCheckError

Diese Funktion prüft die übergebenen SCODE, um festzustellen, ob es sich um einen Fehler handelt.

```
void AFXAPI AfxCheckError(SCODE sc);
throw CMemoryException*
throw COleException*
```

### <a name="remarks"></a>Hinweise

Wenn es sich um einen Fehler handelt, wird die Funktion eine Ausnahme ausgelöst. Wenn der übergebene SCODE E_OUTOFMEMORY ist, löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) durch Aufrufen von [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception). Andernfalls löst die Funktion eine [COleException](../../mfc/reference/coleexception-class.md) durch Aufrufen von [AfxThrowOleException](exception-processing.md#afxthrowoleexception).

Diese Funktion kann verwendet werden, um die Rückgabewerte von Aufrufen von OLE-Funktionen in Ihrer Anwendung zu überprüfen. Den Rückgabewert mit dieser Funktion in Ihrer Anwendung testen, können Sie Sie auf fehlerbedingungen mit einer minimalen Menge an Code ordnungsgemäß reagieren.

> [!NOTE]
>  Diese Funktion hat dieselbe Wirkung im Debugmodus aus, und nicht-Debugbuilds.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#33](../../mfc/codesnippet/cpp/diagnostic-services_10.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxcheckmemory"></a>  AfxCheckMemory

Diese Funktion überprüft den freien Speicherpool und gibt Fehlermeldungen nach Bedarf.

```
BOOL  AfxCheckMemory();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn keine Speicherfehler; andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn die Funktion keine Beschädigung erkannt wird, wird nichts ausgegeben.

Alle Speicherblöcke, die derzeit auf dem Heap reserviert werden überprüft, einschließlich von zugeordneten **neue** aber nicht die vom zugrunde liegenden speicherzuordnungen, direkte Aufrufe zugeordnet sind, z. B. die **Malloc** Funktion oder die `GlobalAlloc` Windows-Funktion. Wenn ein beliebiger Block gefunden wird, ist möglicherweise beschädigt, wird eine Nachricht an die Ausgabe des Debuggers ausgegeben.

Wenn Sie die Zeile einfügen

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

in einem Programmmodul, klicken Sie dann für nachfolgende Aufrufe von `AfxCheckMemory` zeigen die Anzahl von Dateinamen und Zeilennummern, in dem der Speicher belegt wurde.

> [!NOTE]
>  Wenn Ihr Modul enthält eine oder mehrere Implementierungen von serialisierbare Klassen, müssen Sie setzen das `#define` Zeile nach dem letzten Aufruf der IMPLEMENT_SERIAL-Makro.

Diese Funktion kann nur in der Debugversion von MFC.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCObjectSample#26](../../mfc/codesnippet/cpp/diagnostic-services_11.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxdump"></a>  AfxDump (MFC)

Mit dieser Funktion werden im Debugger, um den Zustand eines Objekts während des Debuggens zu sichern.

```
void AfxDump(const CObject* pOb);
```

### <a name="parameters"></a>Parameter

*Geschäftssitz*<br/>
Ein Zeiger auf ein Objekt einer Klasse abgeleitet `CObject`.

### <a name="remarks"></a>Hinweise

`AfxDump` Ruft ein Objekt des `Dump` Memberfunktion und sendet die Informationen zu dem Speicherort angegeben wird, durch die `afxDump` Variable. `AfxDump` ist nur in der Debugversion des MFC-verfügbar.

Programmcode sollte nicht aufrufen `AfxDump`, aber Sie sollten stattdessen aufrufen, die `Dump` -Memberfunktion des entsprechenden Objekts.

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

### <a name="see-also"></a>Siehe auch

[CObject::Dump](cobject-class.md#dump)

##  <a name="afxdumpstack"></a>  AfxDumpStack

Diese globale Funktion kann verwendet werden, ein Image des aktuellen Stapels generiert wird.

```
void AFXAPI AfxDumpStack(DWORD dwTarget = AFX_STACK_DUMP_TARGET_DEFAULT);
```

### <a name="parameters"></a>Parameter

*dwTarget*<br/>
Gibt an, das Ziel der Dump ausgegeben. Mögliche Werte, die mit der bitweisen OR kombiniert werden können ( **&#124;**)-Operator, lauten wie folgt:

- Ausgabe von AFX_STACK_DUMP_TARGET_TRACE sendet die [ABLAUFVERFOLGUNG](#trace) Makro. Das TRACE-Makro generiert die Ausgabe in Debugversionen nur; Es wird keine Ausgabe generiert, in Releasebuilds. Darüber hinaus kann die ABLAUFVERFOLGUNG für andere Ziele neben der Debugger umgeleitet werden.

- Sichern von Ausgabe an das Standardziel AFX_STACK_DUMP_TARGET_DEFAULT sendet. Für einen Debugbuild erfolgt die Ausgabe in das TRACE-Makro. In einem Releasebuild erfolgt die Ausgabe in die Zwischenablage.

- AFX_STACK_DUMP_TARGET_CLIPBOARD sendet die Ausgabe in die Zwischenablage nur. Die Daten befindet sich in der Zwischenablage als nur-Text mithilfe der HIERSVR Zwischenablageformat.

- AFX_STACK_DUMP_TARGET_BOTH sendet die Ausgabe in die Zwischenablage und das TRACE-Makro gleichzeitig.

- Ausgabe direkt an den Debugger mithilfe der Win32-Funktion sendet AFX_STACK_DUMP_TARGET_ODS `OutputDebugString()`. Diese Option generiert Debuggerausgabe in sowohl für Debug- und Releasebuilds, wenn ein Debugger an den Prozess angefügt ist. AFX_STACK_DUMP_TARGET_ODS erreicht den Debugger immer, (Wenn sie angefügt ist) und kann nicht umgeleitet werden.

### <a name="remarks"></a>Hinweise

Das folgende Beispiel gibt die eine einzelne Zeile der Ausgabe von Aufrufen generiert `AfxDumpStack` aus einem Schaltflächenhandler in einer MFC-Dialogfeld-Anwendung:

```Output
=== begin AfxDumpStack output ===
00427D55: DUMP2\DEBUG\DUMP2.EXE! void AfxDumpStack(unsigned long) + 181 bytes
0040160B: DUMP2\DEBUG\DUMP2.EXE! void CDump2Dlg::OnClipboard(void) + 14 bytes
0044F884: DUMP2\DEBUG\DUMP2.EXE! int _AfxDispatchCmdMsg(class CCmdTarget *,
unsigned int,int,void ( CCmdTarget::*)(void),void *,unsigned int,struct
AFX_CMDHANDLE
0044FF7B: DUMP2\DEBUG\DUMP2.EXE! virtual int CCmdTarget::OnCmdMsg(unsigned
int,int,void *,struct AFX_CMDHANDLERINFO *) + 626 bytes
00450C71: DUMP2\DEBUG\DUMP2.EXE! virtual int CDialog::OnCmdMsg(unsigned
int,int,void *,struct AFX_CMDHANDLERINFO *) + 36 bytes
00455B27: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnCommand(unsigned
int,long) + 312 bytes
00454D3D: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnWndMsg(unsigned
int,unsigned int,long,long *) + 83 bytes
00454CC0: DUMP2\DEBUG\DUMP2.EXE! virtual long CWnd::WindowProc(unsigned
int,unsigned int,long) + 46 bytes
004528D9: DUMP2\DEBUG\DUMP2.EXE! long AfxCallWndProc(class CWnd *,struct
HWND__ *,unsigned int,unsigned int,long) + 237 bytes
00452D34: DUMP2\DEBUG\DUMP2.EXE! long AfxWndProc(struct HWND__ *,unsigned
int,unsigned int,long) + 129 bytes
BFF73663: WINDOWS\SYSTEM\KERNEL32.DLL! ThunkConnect32 + 2148 bytes
BFF928E0: WINDOWS\SYSTEM\KERNEL32.DLL! UTUnRegister + 2492 bytes
=== end AfxDumpStack() output ===
```

Jede Zeile in der obigen Ausgabe gibt an, die Adresse der dem letzten Funktionsaufruf, der vollständige Name des Moduls, das den Funktionsaufruf und der Funktionsprototyp Namens enthält. Wenn der Funktionsaufruf im Stapel nicht auf die genaue Adresse der Funktion erfolgen, wird ein Offset von Bytes angezeigt.

In der folgende Tabelle werden beispielsweise die erste Zeile der obigen Ausgabe beschrieben:

|Output|Beschreibung|
|------------|-----------------|
|`00427D55:`|Die Rückgabeadresse der dem letzten Funktionsaufruf.|
|`DUMP2\DEBUG\DUMP2.EXE!`|Der vollständige Name des Moduls, das den Funktionsaufruf enthält.|
|`void AfxDumpStack(unsigned long)`|Der Funktionsprototyp aufgerufen.|
|`+ 181 bytes`|Der Offset in Bytes, die von der Adresse von der Funktionsprototyp (in diesem Fall `void AfxDumpStack(unsigned long)`) an die Rücksendeadresse (in diesem Fall `00427D55`).|

`AfxDumpStack` ist im Debug- und aufgeführt Produktversionen von MFC-Bibliotheken verfügbar. jedoch ist die Funktion immer statisch verknüpft, auch wenn Ihre ausführbare Datei MFC in einer gemeinsam genutzten DLL verwendet. Im shared-Library-Implementierungen ist die Funktion in der MFCS42 gefunden. LIB-Bibliothek (und dessen Varianten).

Diese Funktion erfolgreich verwenden zu können:

- Die Datei IMAGEHLP. DLL muss auf Ihrem Pfad befinden. Wenn Sie nicht über diese DLL-Datei verfügen, wird die Funktion eine Fehlermeldung angezeigt. Finden Sie unter [Image-Hilfe-Bibliothek](/windows/desktop/Debug/image-help-library) Informationen zu den von IMAGEHLP bereitgestellte Funktion.

- Die Module, die Frames im Stapel müssen Debuginformationen einschließen. Wenn sie keine Debuginformationen enthalten, die Funktion generiert eine stapelüberwachung nach wie vor, aber die Ablaufverfolgung weniger detailliert.
  ### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxenablememoryleakdump"></a>  AfxEnableMemoryLeakDump

Aktiviert und deaktiviert das Speicherabbild des Arbeitsspeicherverlusts im Destruktor AFX_DEBUG_STATE.

```
BOOL AFXAPI AfxEnableMemoryLeakDump(BOOL bDump);
```

### <a name="parameters"></a>Parameter

*bDump*<br/>
[in] TRUE gibt an, dass das Speicherabbild des Arbeitsspeicherverlusts aktiviert ist; FALSE gibt an, dass das Speicherabbild des Arbeitsspeicherverlusts deaktiviert ist.

### <a name="return-value"></a>Rückgabewert

Der vorherige Wert für dieses Flag.

### <a name="remarks"></a>Hinweise

Wenn eine Anwendung die MFC-Bibliothek entlädt, führt die MFC-Bibliothek eine Überprüfung auf Speicherverluste aus. An diesem Punkt werden alle Speicherverluste gemeldet, um den Benutzer durch die **Debuggen** Fenster von Visual Studio.

Wenn Ihre Anwendung eine andere Bibliothek vor der MFC-Bibliothek lädt, werden einige Speicherbelegungen in dieser Bibliothek fälschlicherweise als Arbeitsspeicherverluste gemeldet. Wegen Arbeitsspeicherverlusten, die eigentlich keine sind, wird Ihre Anwendung möglicherweise langsam beendet, da die MFC-Bibliothek die Speicherverluste meldet. Verwenden Sie in diesem Fall `AfxEnableMemoryLeakDump` , um das Speicherabbild des Arbeitsspeicherverlusts zu deaktivieren.

> [!NOTE]
>  Wenn Sie diese Methode verwenden, um das Speicherabbild des Arbeitsspeicherverlusts deaktivieren, erhalten Sie keine Berichte über tatsächliche Arbeitsspeicherverluste in Ihrer Anwendung. Sie sollten diese Methode nur verwenden, wenn Sie sicher sind, dass der Bericht über die Arbeitsspeicherverluste falsche Meldungen enthält.

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxenablememorytracking"></a>  AfxEnableMemoryTracking

Diagnose speicherüberwachung ist normalerweise in der Debugversion von MFC aktiviert.

```
BOOL AfxEnableMemoryTracking(BOOL bTrack);
```

### <a name="parameters"></a>Parameter

*bTrack*<br/>
Durch Festlegen dieses Werts auf "true" für die Arbeitsspeicher-nachverfolgung; FALSE schaltet dies aus.

### <a name="return-value"></a>Rückgabewert

Die vorherige Einstellung des Flags Überwachung zu aktivieren.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion deaktivieren der nachverfolgung auf Abschnitte des Codes, die Sie kennen Blöcke ordnungsgemäß zugeordnet werden.

Weitere Informationen zu `AfxEnableMemoryTracking`, finden Sie unter [MFC-Anwendungen Debuggen](/visualstudio/debugger/mfc-debugging-techniques).

> [!NOTE]
>  Diese Funktion kann nur in der Debugversion von MFC.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#24](../../mfc/codesnippet/cpp/diagnostic-services_12.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxismemoryblock"></a>  AfxIsMemoryBlock

Testet eine Speicheradresse, stellen Sie sicher, dass es einen aktiven Speicherblock, der von der Diagnose Version der belegt wurde **neue**.

```
BOOL AfxIsMemoryBlock(
    const void* p,
    UINT nBytes,
    LONG* plRequestNumber = NULL);
```

### <a name="parameters"></a>Parameter

*p*<br/>
Verweist auf den Speicherblock, der getestet werden.

*nBytes*<br/>
Enthält die Länge des Speicherblocks in Bytes.

*plRequestNumber*<br/>
Verweist auf eine **lange** ganze Zahl, die wird mit der Sequenznummer für den Speicherblock Zuordnung gefüllt werden soll, oder NULL, wenn es keine aktiven Speicherblocks darstellt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn der Speicherblock derzeit belegt ist und die Länge richtig; andernfalls 0.

### <a name="remarks"></a>Hinweise

Außerdem überprüft die angegebene Größe für die ursprüngliche zugeordnete Größe. Wenn die Funktion ungleich NULL zurückgibt, wird die Sequenznummer der Zuordnung zurückgegeben *PlRequestNumber*. Diese Zahl steht für die Reihenfolge, in dem der Block, relativ zu allen anderen belegt wurde **neue** Zuordnungen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#27](../../mfc/codesnippet/cpp/diagnostic-services_13.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxisvalidaddress"></a>  AfxIsValidAddress

Prüft jede beliebige Speicheradresse aus, um sicherzustellen, dass sie vollständig innerhalb des Programms Speicherbereich enthalten ist.

```
BOOL AfxIsValidAddress(
    const void* lp,
    UINT nBytes,
    BOOL bReadWrite = TRUE);
```

### <a name="parameters"></a>Parameter

*LP*<br/>
Verweist auf die Speicheradresse, die getestet werden.

*nBytes*<br/>
Enthält die Anzahl der Bytes an Arbeitsspeicher, der getestet werden.

*bReadWrite*<br/>
Gibt an, ob der Speicher sowohl zum Lesen und Schreiben (TRUE) oder nur zu lesen (FALSE).

### <a name="return-value"></a>Rückgabewert

In Debugbuilds ist ungleich NULL, wenn der angegebene Speicher blockieren vollständig innerhalb des Programms Speicherbereich enthalten; andernfalls 0.

In den nichtdebugversionen einen Wert ungleich NULL *Lp* nicht NULL ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Adresse ist nicht beschränkt auf Blöcke von zugeordneten **neue**.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#28](../../mfc/codesnippet/cpp/diagnostic-services_14.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxisvalidstring"></a>  AfxIsValidString

Verwenden Sie diese Funktion, um zu bestimmen, ob ein Zeiger auf eine Zeichenfolge gültig ist.

```
BOOL  AfxIsValidString(
    LPCSTR lpsz,
    int nLength = -1);
```

### <a name="parameters"></a>Parameter

*lpsz*<br/>
Der Zeiger, um zu testen.

*nLength*<br/>
Gibt die Länge der Zeichenfolge, die getestet werden, in Bytes. Der Wert-1 gibt an, dass die Zeichenfolge Null-terminiert ist.

### <a name="return-value"></a>Rückgabewert

In Debugbuilds ungleich NULL, wenn der angegebene Zeiger auf eine Zeichenfolge der angegebenen Größe verweist; andernfalls 0.

In den nichtdebugversionen einen Wert ungleich NULL *Lpsz* nicht NULL ist; andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#29](../../mfc/codesnippet/cpp/diagnostic-services_15.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxsetallochook"></a>  AfxSetAllocHook

Legt einen Hook, mit dem Aufruf der angegebenen Funktion kann, bevor jeder Speicherblock zugeordnet wird.

```
AFX_ALLOC_HOOK AfxSetAllocHook(AFX_ALLOC_HOOK pfnAllocHook);
```

### <a name="parameters"></a>Parameter

*pfnAllocHook*<br/>
Gibt den Namen der aufzurufenden Funktion. Finden Sie unter den Hinweisen für den Prototyp einer Zuordnung-Funktion.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn Sie die Zuordnung zulassen möchten; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Microsoft Foundation Class-Bibliothek Debug-Speicherreservierungsfunktion kann aufrufen, damit die Benutzer aus, um eine speicherbelegung zu überwachen und zu steuern, ob die Zuordnung zulässig ist eine benutzerdefinierte Hookfunktion. Hookfunktionen lauten wie folgt Prototyp:

**"Bool" AFXAPI AllocHook (Size_t** `nSize` **, "bool"** `bObject` **langen** `lRequestNumber` **);**

*nSize*<br/>
Die Größe der vorgeschlagenen speicherbelegung.

*bObject*<br/>
TRUE, wenn die Zuordnung für eine `CObject`-abgeleitetes Objekt; andernfalls "false".

*lRequestNumber*<br/>
Die speicherbelegung Sequenznummer.

Beachten Sie, dass die Aufrufkonvention AFXAPI impliziert, dass der aufgerufene die Parameter aus dem Stapel entfernen muss.

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxdoforallclasses"></a>  AfxDoForAllClasses

Ruft die angegebene Iteration-Funktion für alle serialisierbaren `CObject`-abgeleiteten Klassen im Speicherbereich von der Anwendung.

```
void
AFXAPI AfxDoForAllClasses(
    void (* pfn)(const CRuntimeClass* pClass, void* pContext),
    void* pContext);
```

### <a name="parameters"></a>Parameter

*pfn*<br/>
Verweist auf eine Iteration-Funktion, die für jede Klasse aufgerufen werden. Die Funktionsargumente sind ein Zeiger auf eine `CRuntimeClass` -Objekt und einen void-Zeiger auf zusätzliche Daten, die der Aufrufer der Funktion angibt.

*pContext*<br/>
Verweist auf die optionalen Daten, die der Aufrufer der Funktion für die Iteration angeben kann. This-Zeiger kann NULL sein.

### <a name="remarks"></a>Hinweise

Serialisierbare `CObject`-abgeleiteten Klassen sind Klassen, die mit dem DECLARE_SERIAL-Makro abgeleitet. Der Zeiger, der an übergebene `AfxDoForAllClasses` in *"pContext"* wird bei jedem Aufruf an die angegebene Iteration-Funktion übergeben.

> [!NOTE]
>  Diese Funktion kann nur in der Debugversion von MFC.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#113](../../mfc/codesnippet/cpp/diagnostic-services_16.cpp)]

[!code-cpp[NVC_MFCCollections#114](../../mfc/codesnippet/cpp/diagnostic-services_17.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxdoforallobjects"></a>  AfxDoForAllObjects

Die angegebene Iteration-Funktion ausgeführt wird, für alle Objekte aus abgeleitete `CObject` , zugeteilt wurde mit **neue**.

```
void AfxDoForAllObjects(
    void (* pfn)(CObject* pObject, void* pContext),
    void* pContext);
```

### <a name="parameters"></a>Parameter

*pfn*<br/>
Zeigt auf eine Iteration-Funktion, die für jedes Objekt ausgeführt. Die Funktionsargumente sind ein Zeiger auf eine `CObject` und einen void-Zeiger auf zusätzliche Daten, die der Aufrufer der Funktion angibt.

*pContext*<br/>
Verweist auf die optionalen Daten, die der Aufrufer der Funktion für die Iteration angeben kann. This-Zeiger kann NULL sein.

### <a name="remarks"></a>Hinweise

Stapel, globale oder eingebettete Objekte werden nicht aufgezählt. Der Zeiger übergeben wird, um `AfxDoForAllObjects` in *"pContext"* wird bei jedem Aufruf an die angegebene Iteration-Funktion übergeben.

> [!NOTE]
>  Diese Funktion kann nur in der Debugversion von MFC.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#115](../../mfc/codesnippet/cpp/diagnostic-services_18.cpp)]

[!code-cpp[NVC_MFCCollections#116](../../mfc/codesnippet/cpp/diagnostic-services_19.cpp)]

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
