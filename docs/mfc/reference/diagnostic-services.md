---
title: Diagnosedienste
ms.date: 11/04/2016
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
ms.openlocfilehash: 4cf3f53d1e238218b4eb892dc92e3c823dcc1296
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630516"
---
# <a name="diagnostic-services"></a>Diagnosedienste

Die Microsoft Foundation Class-Bibliothek bietet viele Diagnosedienste, die das Debuggen von Programmen erleichtern. Zu diesen Diagnosediensten zählen Makros und globale Funktionen, die Ihnen das Nachverfolgen der Speicherzuweisungen von Programmen, das Sichern des Inhalts von Objekten zur Laufzeit und das Ausgeben von Debugmeldungen zur Laufzeit ermöglichen. Die Makros und globalen Funktionen für Diagnosedienste sind in folgende Kategorien gruppiert:

- Allgemeine Diagnosemakros

- Allgemeine Diagnosefunktionen und -Variablen

- Objektdiagnosefunktionen

Diese Makros und Funktionen stehen in den Debug- und den endgültigen Produktversionen von MFC für alle von `CObject` abgeleiteten Klassen zur Verfügung. Allerdings wird mit Ausnahme von DEBUG_NEW und Verify nichts in der Releaseversion durchführen.

In der Debugbibliothek stehen alle zugewiesenen Speicherblöcke in aus einer Reihe von "Wächterbytes" bestehenden Klammern. Wenn diese Bytes durch einen fehlerhaften Schreibzugriff auf den Speicher gestört werden, können die Diagnoseroutinen ein Speicherproblem melden. Wenn Sie diese Zeile:

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

in Ihre Implementierungsdatei einschließen, werden für jeden Aufruf von **new** der Dateiname und die Zeilennummer gespeichert, für die die Speicherzuweisung erfolgt ist. Die Funktion [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince) zeigt diese Zusatzinformationen an, was Ihnen das Erkennen von Speicherverlusten ermöglicht. Weitere Informationen zur Diagnoseausgabe finden Sie auch bei der Klasse [CDumpContext](../../mfc/reference/cdumpcontext-class.md) .

Darüber hinaus unterstützt die C-Laufzeitbibliothek auch eine Reihe von Diagnosefunktionen, die Sie zum Debuggen von Anwendungen verwenden können. Weitere Informationen finden Sie unter [Debugroutinen](../../c-runtime-library/debug-routines.md) in der Referenz zur Laufzeitbibliothek.

### <a name="mfc-general-diagnostic-macros"></a>Allgemeine MFC-Diagnosemakros

|||
|-|-|
|[ASSERT](#assert)|Gibt eine Meldung aus und bricht dann das Programm ab, wenn der angegebene Ausdruck in der Debugversion der Bibliothek als false ausgewertet wird.|
|[ASSERT_KINDOF](#assert_kindof)|Prüft, ob ein Objekt ein Objekt der angegebenen Klasse oder einer aus der angegebenen Klasse abgeleiteten Klasse ist.|
|[ASSERT_VALID](#assert_valid)|Prüft die interne Gültigkeit eines Objekts durch Aufrufen seiner `AssertValid` -Memberfunktion; normalerweise durch `CObject`außer Kraft gesetzt.|
|[DEBUG_NEW](#debug_new)|Gibt einen Dateinamen und eine Zeilennummer für alle Objektzuweisungen im Debugmodus an, um die Suche nach Speicherverlusten zu unterstützen.|
|[DEBUG_ONLY](#debug_only)|Ähnelt Assert, aber testet nicht den Wert des Ausdrucks. nützlich für Code, der nur im Debugmodus ausgeführt werden soll.|
|[Sicher und ENSURE_VALID](#ensure)|Verwenden Sie, um Daten Richtigkeit zu überprüfen.|
|[THIS_FILE](#this_file)|Wird auf den Namen der Datei erweitert, die kompiliert wird.|
|[TRACE](#trace)|Stellt eine `printf`-ähnliche Funktionalität in der Debugversion der Bibliothek zur Verfügung.|
|[VERIFY](#verify)|Ähnlich wie Assert, wertet jedoch den Ausdruck in der Releaseversion der Bibliothek sowie in der Debugversion aus.|

### <a name="mfc-general-diagnostic-variables-and-functions"></a>Allgemeine MFC-Diagnosevariablen und -Funktionen

|||
|-|-|
|[afxDump](#afxdump)|Globale Variable, die [CDumpContext](../../mfc/reference/cdumpcontext-class.md) -Informationen an das Debuggerausgabefenster oder das Debugterminal sendet.|
|[afxMemDF](#afxmemdf)|Globale Variable, die das Verhalten der Debugspeicherzuweisung steuert.|
|[AfxCheckError](#afxcheckerror)|Eine globale Variable, die zum Testen des bestandenen scodes verwendet wird, um festzustellen, ob es sich um einen Fehler handelt|
|[AfxCheckMemory](#afxcheckmemory)|Überprüft die Integrität des gesamten derzeit zugewiesenen Speichers.|
|[AfxDebugBreak](#afxdebugbreak)|Verursacht eine Unterbrechung der Ausführung.|
|[AfxDump](#cdumpcontext_in_mfc)|Sichert bei einem Aufruf im Debugger den Status eines Objekts während des Debuggens.|
|[AfxDump](#afxdump)|Interne Funktion, die den Zustand eines Objekts beim Debuggen sichert.|
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

### <a name="mfc-compilation-macros"></a>MFC-Kompilierungs Makros

|||
|-|-|
|[_AFX_SECURE_NO_WARNINGS](#afx_secure_no_warnings)|Unterdrückt Compilerwarnungen für die Verwendung von veralteten MFC-Funktionen.|

## <a name="afx_secure_no_warnings"></a> _AFX_SECURE_NO_WARNINGS

Unterdrückt Compilerwarnungen für die Verwendung von veralteten MFC-Funktionen.

### <a name="syntax"></a>Syntax

```
_AFX_SECURE_NO_WARNINGS
```

### <a name="example"></a>Beispiel

Dieses Codebeispiel führt zu einer Compilerwarnung, wenn _AFX_SECURE_NO_WARNINGS nicht definiert wurde.

```cpp
// define this before including any afx files in *pch.h* (*stdafx.h* in Visual Studio 2017 and earlier)
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

Rufen Sie diese Funktion auf, um während der Ausführung der Debugversion Ihrer `AfxDebugBreak`MFC-Anwendung eine Unterbrechung (an der Position des Aufrufes von) auszulösen.

### <a name="syntax"></a>Syntax

```
void AfxDebugBreak( );
```

### <a name="remarks"></a>Hinweise

`AfxDebugBreak`hat keine Auswirkungen auf die Releaseversionen einer MFC-Anwendung und sollte entfernt werden. Diese Funktion sollte nur in MFC-Anwendungen verwendet werden. Verwenden Sie die Win32-API `DebugBreak`-Version,, um eine Unterbrechung in nicht-MFC-Anwendungen zu verursachen.

### <a name="requirements"></a>Anforderungen

**Header:** afxver_. h

##  <a name="assert"></a>  ASSERT

Wertet das zugehörige Argument aus.

```
ASSERT(booleanExpression)
```

### <a name="parameters"></a>Parameter

*booleanExpression*<br/>
Gibt einen Ausdruck an (einschließlich Zeiger Werten), der als ungleich 0 (null) oder 0 ausgewertet wird.

### <a name="remarks"></a>Hinweise

Wenn das Ergebnis 0 ist, druckt das-Makro eine Diagnose Meldung und bricht das Programm ab. Wenn die Bedingung ungleich 0 (null) ist, wird keine Aktion durchführt.

Die Diagnosemeldung hat die Form

`assertion failed in file <name> in line <num>`

Dabei ist *Name* der Name der Quelldatei, und *NUM* ist die Zeilennummer der fehlgeschlagenen fehlgeschlagenen in der Quelldatei.

In der Releaseversion von MFC wertet Assert den Ausdruck nicht aus und unterbricht das Programm daher nicht. Wenn der Ausdruck unabhängig von der Umgebung ausgewertet werden muss, verwenden Sie das VERIFY-Makro anstelle von Assert.

> [!NOTE]
>  Diese Funktion ist nur in der Debugversion von MFC verfügbar.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#44](../../mfc/codesnippet/cpp/diagnostic-services_2.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="assert_kindof"></a>  ASSERT_KINDOF

Dieses Makro bestätigt, dass das Objekt, auf das verwiesen wird, ein Objekt der angegebenen Klasse oder ein Objekt einer Klasse ist, die von der angegebenen Klasse abgeleitet ist.

```
ASSERT_KINDOF(classname, pobject)
```

### <a name="parameters"></a>Parameter

*classname*<br/>
Der Name einer `CObject`von abgeleiteten Klasse.

*pObject*<br/>
Ein Zeiger auf ein Klassenobjekt.

### <a name="remarks"></a>Hinweise

Der *pObject* -Parameter muss ein Zeiger auf ein Objekt sein und kann **konstant**sein. Das Objekt, auf das verwiesen wird, und `CObject` die-Klasse müssen Lauf Zeit Klassen Informationen unterstützen. Um z. b. sicherzustellen `pDocument` , dass es sich um einen Zeiger auf `CMyDoc` ein Objekt der Klasse oder einen der zugehörigen Ableitungen handelt, könnten Sie Folgendes programmieren:

[!code-cpp[NVC_MFCDocView#194](../../mfc/codesnippet/cpp/diagnostic-services_3.cpp)]

Die Verwendung `ASSERT_KINDOF` des Makros ist identisch mit der Codierung:

[!code-cpp[NVC_MFCDocView#195](../../mfc/codesnippet/cpp/diagnostic-services_4.cpp)]

Diese Funktion funktioniert nur für Klassen, die mit dem Makro [DECLARE_DYNAMIC] (Run-Time-Object-Model-Services. MD # DECLARE_DYNAMIC oder [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) ) deklariert wurden.

> [!NOTE]
>  Diese Funktion ist nur in der Debugversion von MFC verfügbar.

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="assert_valid"></a>  ASSERT_VALID

Verwenden Sie, um Ihre Annahmen über die Gültigkeit des internen Zustands eines Objekts zu testen.

```
ASSERT_VALID(pObject)
```

### <a name="parameters"></a>Parameter

*pObject*<br/>
Gibt ein Objekt einer von `CObject` abgeleiteten Klasse an, die über eine über schreibende Version `AssertValid` der Member-Funktion verfügt.

### <a name="remarks"></a>Hinweise

ASSERT_VALID Ruft die `AssertValid` Member-Funktion des-Objekts auf, das als Argument übermittelt wird.

In der Releaseversion von MFC führt ASSERT_VALID keine Aktion aus. In der Debugversion überprüft es den Zeiger, überprüft den Wert von NULL und ruft die eigenen `AssertValid` Member-Funktionen des Objekts auf. Wenn einer dieser Tests fehlschlägt, wird eine Warnmeldung auf die gleiche Weise wie [Assert](#assert)angezeigt.

> [!NOTE]
>  Diese Funktion ist nur in der Debugversion von MFC verfügbar.

Weitere Informationen und Beispiele finden Sie unter [Debuggen von MFC-Anwendungen](/visualstudio/debugger/mfc-debugging-techniques).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCObjectSample#19](../../mfc/codesnippet/cpp/diagnostic-services_5.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="debug_new"></a>  DEBUG_NEW

Unterstützt das Auffinden von Speicher Verlusten.

```
#define  new DEBUG_NEW
```

### <a name="remarks"></a>Hinweise

Sie können DEBUG_NEW Everywhere in Ihrem Programm verwenden, das Sie normalerweise den **New** -Operator verwenden, um Heap Speicher zuzuordnen.

Im Debugmodus (wenn das **_DEBUG** -Symbol definiert ist) verfolgt DEBUG_NEW den Dateinamen und die Zeilennummer für jedes Objekt, das zugeordnet wird. Wenn Sie dann die Member-Funktion [CMemoryState::D enpallobjectssince](cmemorystate-structure.md#dumpallobjectssince) verwenden, wird jedes mit DEBUG_NEW zugeordnete Objekt mit dem Dateinamen und der Zeilennummer, in der es zugeordnet wurde, angezeigt.

Um DEBUG_NEW zu verwenden, fügen Sie die folgende Direktive in die Quelldateien ein:

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

Nachdem Sie diese Direktive eingefügt haben, fügt der Präprozessor DEBUG_NEW an der Stelle ein, an der Sie **neu**verwenden, und MFC übernimmt den Rest. Wenn Sie eine Releaseversion des Programms kompilieren, wird DEBUG_NEW zu einem einfachen **neuen** Vorgang aufgelöst, und die Informationen zum Dateinamen und zur Zeilennummer werden nicht generiert.

> [!NOTE]
>  In früheren Versionen von MFC (4,1 und früher) mussten Sie die `#define` Anweisung nach allen Anweisungen platzieren, die die Makros IMPLEMENT_DYNCREATE oder IMPLEMENT_SERIAL aufgerufen haben. Dies ist nicht mehr erforderlich.

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="debug_only"></a>  DEBUG_ONLY

Im Debugmodus (wenn das **_DEBUG** -Symbol definiert ist) wertet DEBUG_ONLY sein Argument aus.

```
DEBUG_ONLY(expression)
```

### <a name="remarks"></a>Hinweise

In einem Releasebuild wertet DEBUG_ONLY das zugehörige Argument nicht aus. Dies ist nützlich, wenn Sie über Code verfügen, der nur in Debugbuilds ausgeführt werden soll.

Das DEBUG_ONLY-Makro entspricht dem umgebenden *Ausdruck* mit `#ifdef _DEBUG` und `#endif`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#32](../../mfc/codesnippet/cpp/diagnostic-services_6.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

### <a name="ensure"></a>Sicher und ENSURE_VALID

Verwenden Sie, um Daten Richtigkeit zu überprüfen.

### <a name="syntax"></a>Syntax

```
ENSURE(  booleanExpression )
ENSURE_VALID( booleanExpression  )
```

### <a name="parameters"></a>Parameter

*booleanExpression*<br/>
Gibt einen booleschen Ausdruck an, der getestet werden soll.

### <a name="remarks"></a>Hinweise

Der Zweck dieser Makros besteht darin, die Validierung von Parametern zu verbessern. Die Makros verhindern die weitere Verarbeitung falscher Parameter in Ihrem Code. Im Gegensatz zu Assert-Makros lösen die sicherstellen, dass neben der Erstellung einer-Behauptung eine Ausnahme ausgelöst wird.

Die Makros Verhalten sich auf zwei Arten, entsprechend der Projekt Konfiguration. Die Makros wenden Assert an und lösen dann eine Ausnahme aus, wenn die-Übersetzung fehlschlägt. In Debugkonfigurationen (d. h., wo _DEBUG definiert ist) ergeben die Makros daher eine-Assertion und eine Ausnahme, während die Makros in Releasekonfigurationen nur die Ausnahme ergeben (Assert wertet den Ausdruck in Releasekonfigurationen nicht aus).

Das Makro ENSURE_ARG verhält sich wie das sicherstellen Makro.

ENSURE_VALID Ruft das ASSERT_VALID-Makro auf (das sich nur in Debugbuilds auswirkt). Außerdem löst ENSURE_VALID eine Ausnahme aus, wenn der Zeiger NULL ist. Der NULL-Test wird sowohl in Debug-als auch in Releasekonfigurationen ausgeführt.

Wenn einer dieser Tests fehlschlägt, wird eine Warnmeldung auf die gleiche Weise wie Assert angezeigt. Das-Makro löst bei Bedarf eine Ausnahme für ein ungültiges Argument aus.
### <a name="requirements"></a>Anforderungen

**Header:** afx.h

## <a name="this_file"></a>THIS_FILE

Wird auf den Namen der Datei erweitert, die kompiliert wird.

### <a name="syntax"></a>Syntax

```
THIS_FILE
```

### <a name="remarks"></a>Hinweise

Die Informationen werden von den Makros Assert und Verify verwendet. Der Anwendungs-Assistent und die Code-Assistenten platzieren das Makro in Quell Code Dateien, die Sie erstellen.

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

##  <a name="trace"></a>  TRACE

Sendet die angegebene Zeichenfolge an den Debugger der aktuellen Anwendung.

```
TRACE(exp)
TRACE(DWORD  category,  UINT  level, LPCSTR lpszFormat, ...)
```

### <a name="remarks"></a>Hinweise

Eine Beschreibung der Ablauf Verfolgung finden Sie unter [ATLTRACE2](../../atl/reference/debugging-and-error-reporting-macros.md#atltrace2) . Trace und ATLTRACE2 haben das gleiche Verhalten.

In der Debugversion von MFC sendet dieses Makro die angegebene Zeichenfolge an den Debugger der aktuellen Anwendung. In einem Releasebuild wird dieses Makro in nichts kompiliert (überhaupt kein Code generiert).

Weitere Informationen finden Sie unter [Debuggen von MFC-Anwendungen](/visualstudio/debugger/mfc-debugging-techniques).

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="verify"></a>  VERIFY

Wertet in der Debugversion von MFC das zugehörige Argument aus.

```
VERIFY(booleanExpression)
```

### <a name="parameters"></a>Parameter

*booleanExpression*<br/>
Gibt einen Ausdruck an (einschließlich Zeiger Werten), der als ungleich 0 (null) oder 0 ausgewertet wird.

### <a name="remarks"></a>Hinweise

Wenn das Ergebnis 0 ist, druckt das-Makro eine Diagnose Meldung und hält das Programm an. Wenn die Bedingung ungleich 0 (null) ist, wird keine Aktion durchführt.

Die Diagnosemeldung hat die Form

`assertion failed in file <name> in line <num>`

Dabei ist *Name* der Name der Quelldatei und *NUM* die Zeilennummer der fehlgeschlagenen Fehler in der Quelldatei.

In der Releaseversion von MFC wertet Verify den Ausdruck aus, druckt oder unterbricht das Programm jedoch nicht. Wenn der Ausdruck z. b. ein Funktions Aufrufwert ist, wird der-Vorgang durchgeführt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#198](../../mfc/codesnippet/cpp/diagnostic-services_7.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="cdumpcontext_in_mfc"></a>afxDump (CDumpContext in MFC)

Stellt grundlegende Objekt Sicherungsfunktionen in Ihrer Anwendung bereit.

```
CDumpContext  afxDump;
```

### <a name="remarks"></a>Hinweise

`afxDump`ist ein vordefiniertes [CDumpContext](../../mfc/reference/cdumpcontext-class.md) -Objekt, mit `CDumpContext` dem Sie Informationen an das Debugger-Ausgabefenster oder an ein Debug-Terminal senden können. In der Regel stellen `afxDump` Sie als Parameter für `CObject::Dump`bereit.

Unter Windows NT und allen Versionen von Windows wird `afxDump` die Ausgabe an das Fenster Output-Debug von Visual C++ gesendet, wenn Sie die Anwendung debuggen.

Diese Variable wird nur in der Debugversion von MFC definiert. Weitere Informationen zu finden `afxDump`Sie unter [Debuggen von MFC-Anwendungen](/visualstudio/debugger/mfc-debugging-techniques).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#23](../../mfc/codesnippet/cpp/diagnostic-services_8.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

## <a name="afxdump"></a>AfxDump (intern)

Interne Funktion, die MFC zum Sichern des Zustands eines Objekts beim Debuggen verwendet.

### <a name="syntax"></a>Syntax

```
void AfxDump(const CObject* pOb);
```

### <a name="parameters"></a>Parameter

*pOb*<br/>
Ein Zeiger auf ein Objekt einer Klasse, die von `CObject`abgeleitet ist.

### <a name="remarks"></a>Hinweise

`AfxDump`Ruft die Member- `Dump` Funktion eines Objekts auf und sendet die Informationen an den Speicherort `afxDump` , der von der Variablen angegeben wird. `AfxDump`ist nur in der Debugversion von MFC verfügbar.

Der Programmcode sollte nicht aufgerufen `AfxDump`werden, sondern sollte stattdessen die `Dump` Member-Funktion des entsprechenden Objekts aufzurufen.

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxmemdf"></a>  afxMemDF

Auf diese Variable kann von einem Debugger oder Programm aus zugegriffen werden, und Sie können die Zuordnungs Diagnose optimieren.

```
int  afxMemDF;
```

### <a name="remarks"></a>Hinweise

`afxMemDF`kann die folgenden Werte aufweisen, wie von der-Enumeration `afxMemDF`angegeben:

- `allocMemDF`Aktiviert die debugzuweisung (Standardeinstellung in der Debugbibliothek).

- `delayFreeMemDF`Verzögerungen bei der Freigabe von Speicher. Während das Programm einen Speicherblock freigibt, wird dieser Arbeitsspeicher von der Zuweisung nicht an das zugrunde liegende Betriebssystem zurückgegeben. Dadurch wird die maximale Arbeitsspeicher Belastung für das Programm durchgeführt.

- `checkAlwaysMemDF`Wird `AfxCheckMemory` jedes Mal aufgerufen, wenn Speicher zugeordnet oder freigegeben wird. Dadurch werden Speicher Belegungen und Aufhebungen erheblich langsamer.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#30](../../mfc/codesnippet/cpp/diagnostic-services_9.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxcheckerror"></a>  AfxCheckError

Diese Funktion testet den übergebenen SCODE, um festzustellen, ob es sich um einen Fehler handelt.

```
void AFXAPI AfxCheckError(SCODE sc);
throw CMemoryException*
throw COleException*
```

### <a name="remarks"></a>Hinweise

Wenn es sich um einen Fehler handelt, löst die Funktion eine Ausnahme aus. Wenn der bestandene SCODE E_OUTOFMEMORY ist, löst die Funktion eine [cmemoryexception](../../mfc/reference/cmemoryexception-class.md) aus, indem [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception)aufgerufen wird. Andernfalls löst die Funktion eine [COleException](../../mfc/reference/coleexception-class.md) aus, indem [AfxThrowOleException](exception-processing.md#afxthrowoleexception)aufgerufen wird.

Diese Funktion kann verwendet werden, um die Rückgabewerte von Aufrufen von OLE-Funktionen in der Anwendung zu überprüfen. Indem Sie den Rückgabewert mit dieser Funktion in der Anwendung testen, können Sie mit minimaler Code Menge auf Fehlerbedingungen reagieren.

> [!NOTE]
>  Diese Funktion hat dieselbe Auswirkung in Debug-und nicht-Debugbuilds.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#33](../../mfc/codesnippet/cpp/diagnostic-services_10.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxcheckmemory"></a>  AfxCheckMemory

Diese Funktion überprüft den freien Speicherpool und gibt Fehlermeldungen nach Bedarf aus.

```
BOOL  AfxCheckMemory();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn keine Speicherfehler auftreten. andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn die Funktion keine Speicher Beschädigung erkennt, wird nichts ausgegeben.

Alle Speicherblöcke, die derzeit auf dem Heap zugeordnet sind, werden geprüft. Dies schließt auch die von **neuen** zugeordneten Speicherblöcke ein, aber nicht die, die durch direkte Aufrufe von zugrunde `GlobalAlloc` liegenden Speicherzuweisungen zugewiesen werden, z. b. die **malloc** -Funktion Wenn ein Block als beschädigt festgestellt wird, wird eine Meldung an die Debugger-Ausgabe ausgegeben.

Wenn Sie die Zeile einschließen

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

in einem Programmmodul zeigen nachfolgende Aufrufe von `AfxCheckMemory` den Dateinamen und die Zeilennummer an, in der der Arbeitsspeicher zugeordnet wurde.

> [!NOTE]
>  Wenn das Modul eine oder mehrere Implementierungen serialisierbarer Klassen enthält, müssen Sie die `#define` Zeile nach dem letzten IMPLEMENT_SERIAL-Makro-Befehl platzieren.

Diese Funktion kann nur in der Debugversion von MFC verwendet werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCObjectSample#26](../../mfc/codesnippet/cpp/diagnostic-services_11.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxdump"></a>AfxDump (MFC)

Diese Funktion wird im Debugger aufgerufen, um den Zustand eines Objekts während des Debuggens zu sichern.

```
void AfxDump(const CObject* pOb);
```

### <a name="parameters"></a>Parameter

*pOb*<br/>
Ein Zeiger auf ein Objekt einer Klasse, die von `CObject`abgeleitet ist.

### <a name="remarks"></a>Hinweise

`AfxDump`Ruft die Member- `Dump` Funktion eines Objekts auf und sendet die Informationen an den Speicherort `afxDump` , der von der Variablen angegeben wird. `AfxDump`ist nur in der Debugversion von MFC verfügbar.

Der Programmcode sollte nicht aufgerufen `AfxDump`werden, sondern sollte stattdessen die `Dump` Member-Funktion des entsprechenden Objekts aufzurufen.

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxdumpstack"></a>  AfxDumpStack

Diese globale Funktion kann verwendet werden, um ein Bild des aktuellen Stapels zu generieren.

```
void AFXAPI AfxDumpStack(DWORD dwTarget = AFX_STACK_DUMP_TARGET_DEFAULT);
```

### <a name="parameters"></a>Parameter

*dwTarget*<br/>
Gibt das Ziel der dumpausgabe an. Mögliche Werte, die mit dem bitweisen OR-Operator ( **&#124;** ) kombiniert werden können, lauten wie folgt:

- AFX_STACK_DUMP_TARGET_TRACE sendet die Ausgabe mithilfe des [Trace](#trace) -Makros. Das Trace-Makro generiert die Ausgabe nur in Debugbuilds. in Releasebuilds wird keine Ausgabe generiert. Außerdem kann die Ablauf Verfolgung neben dem Debugger an andere Ziele umgeleitet werden.

- AFX_STACK_DUMP_TARGET_DEFAULT sendet eine dumpausgabe an das Standardziel. Bei einem Debugbuild wird die Ausgabe an das Trace-Makro weitergeleitet. In einem Releasebuild wechselt die Ausgabe in die Zwischenablage.

- AFX_STACK_DUMP_TARGET_CLIPBOARD sendet die Ausgabe nur an die Zwischenablage. Die Daten werden mithilfe des CF_TEXT-Zwischenablage Formats als nur-Text in der Zwischenablage platziert.

- AFX_STACK_DUMP_TARGET_BOTH sendet die Ausgabe gleichzeitig an die Zwischenablage und an das Trace-Makro.

- AFX_STACK_DUMP_TARGET_ODS sendet die Ausgabe mithilfe der Win32-Funktion `OutputDebugString()`direkt an den Debugger. Mit dieser Option wird die Debugger-Ausgabe sowohl in Debug-als auch in Releasebuilds generiert, wenn ein Debugger an den Prozess angefügt wird. AFX_STACK_DUMP_TARGET_ODS erreicht immer den Debugger (wenn er angefügt ist) und kann nicht umgeleitet werden.

### <a name="remarks"></a>Hinweise

Das folgende Beispiel gibt eine einzelne Zeile der Ausgabe wieder, die durch `AfxDumpStack` Aufrufen von einem Schaltflächen Handler in einer MFC-Dialog Anwendung generiert wird:

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

Jede Zeile in der obigen Ausgabe zeigt die Adresse des letzten Funktionsaufrufs, den vollständigen Pfadnamen des Moduls, das den Funktionsaufruf enthält, und den Funktionsprototyp mit dem Namen an. Wenn der Funktions aufrufauf dem Stapel nicht an der exakten Adresse der Funktion ausgeführt wird, wird ein Offset von Bytes angezeigt.

In der folgenden Tabelle wird z. b. die erste Zeile der obigen Ausgabe beschrieben:

|Ausgabe|Beschreibung|
|------------|-----------------|
|`00427D55:`|Die Rückgabeadresse des letzten Funktions Aufrufes.|
|`DUMP2\DEBUG\DUMP2.EXE!`|Der vollständige Pfadname des Moduls, das den Funktions aufzurufen enthält.|
|`void AfxDumpStack(unsigned long)`|Der Funktionsprototyp, der aufgerufen wird.|
|`+ 181 bytes`|Der Offset in Bytes von der Adresse des Funktions Prototyps (in diesem Fall `void AfxDumpStack(unsigned long)`) bis zur Rückgabeadresse (in diesem `00427D55`Fall).|

`AfxDumpStack`ist in Debug-und NonDebug-Versionen der MFC-Bibliotheken verfügbar. die Funktion wird jedoch immer statisch verknüpft, auch wenn die ausführbare Datei MFC in einer freigegebenen DLL verwendet. In Implementierungen der freigegebenen Bibliothek befindet sich die-Funktion in MFCS42. LIB-Bibliothek (und deren Varianten).

So verwenden Sie diese Funktion erfolgreich:

- Die Datei imagehlp. Die dll muss sich in Ihrem Pfad befinden. Wenn Sie nicht über diese DLL verfügen, zeigt die Funktion eine Fehlermeldung an. Informationen zu dem von imagehlp bereitgestellten Funktions Satz finden Sie in der [Bild Hilfe Bibliothek](/windows/win32/Debug/image-help-library) .

- Die Module, die Frames im Stapel enthalten, müssen Debuginformationen enthalten. Wenn Sie keine Debuginformationen enthalten, generiert die Funktion immer noch eine Stapel Überwachung, aber die Ablauf Verfolgung ist weniger detailliert.
  ### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxenablememoryleakdump"></a>Afxenablememoryleakdump

Aktiviert und deaktiviert den Speicher Abbild Speicher im AFX_DEBUG_STATE-debugtor.

```
BOOL AFXAPI AfxEnableMemoryLeakDump(BOOL bDump);
```

### <a name="parameters"></a>Parameter

*bDump*<br/>
in TRUE gibt an, dass das Speicher Abbild Abbild aktiviert ist. FALSE gibt an, dass das Speicher Abbild Abbild deaktiviert ist.

### <a name="return-value"></a>Rückgabewert

Der vorherige Wert für dieses Flag.

### <a name="remarks"></a>Hinweise

Wenn eine Anwendung die MFC-Bibliothek entlädt, führt die MFC-Bibliothek eine Überprüfung auf Speicherverluste aus. An diesem Punkt werden dem Benutzer alle Speicher Verluste über das Fenster **Debuggen** von Visual Studio gemeldet.

Wenn Ihre Anwendung eine andere Bibliothek vor der MFC-Bibliothek lädt, werden einige Speicherbelegungen in dieser Bibliothek fälschlicherweise als Arbeitsspeicherverluste gemeldet. Wegen Arbeitsspeicherverlusten, die eigentlich keine sind, wird Ihre Anwendung möglicherweise langsam beendet, da die MFC-Bibliothek die Speicherverluste meldet. Verwenden Sie in diesem Fall `AfxEnableMemoryLeakDump` , um das Speicherabbild des Arbeitsspeicherverlusts zu deaktivieren.

> [!NOTE]
>  Wenn Sie diese Methode verwenden, um das Speicherabbild des Arbeitsspeicherverlusts deaktivieren, erhalten Sie keine Berichte über tatsächliche Arbeitsspeicherverluste in Ihrer Anwendung. Sie sollten diese Methode nur verwenden, wenn Sie sicher sind, dass der Bericht über die Arbeitsspeicherverluste falsche Meldungen enthält.

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxenablememorytracking"></a>  AfxEnableMemoryTracking

Die Diagnose Speicher Überwachung ist in der Regel in der Debugversion von MFC aktiviert.

```
BOOL AfxEnableMemoryTracking(BOOL bTrack);
```

### <a name="parameters"></a>Parameter

*bTrack*<br/>
Wenn dieser Wert auf true festgelegt wird, wird die Speicher Verfolgung eingeschaltet. FALSE schaltet ihn aus.

### <a name="return-value"></a>Rückgabewert

Die vorherige Einstellung des Flag "Tracking-enable".

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, um das Nachverfolgen von Code Abschnitten zu deaktivieren, die Sie wissen, dass Blöcke ordnungsgemäß zugeordnet werden.

Weitere Informationen zu finden `AfxEnableMemoryTracking`Sie unter [Debuggen von MFC-Anwendungen](/visualstudio/debugger/mfc-debugging-techniques).

> [!NOTE]
>  Diese Funktion kann nur in der Debugversion von MFC verwendet werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#24](../../mfc/codesnippet/cpp/diagnostic-services_12.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxismemoryblock"></a>  AfxIsMemoryBlock

Testet eine Speicheradresse, um sicherzustellen, dass Sie einen aktuell aktiven Speicherblock darstellt, der von der Diagnose Version von **New**zugeordnet wurde.

```
BOOL AfxIsMemoryBlock(
    const void* p,
    UINT nBytes,
    LONG* plRequestNumber = NULL);
```

### <a name="parameters"></a>Parameter

*p*<br/>
Zeigt auf den Speicherblock, der getestet werden soll.

*nBytes*<br/>
Enthält die Länge des Speicherblocks in Bytes.

*plRequestNumber*<br/>
Verweist auf eine **lange** ganze Zahl, die mit der Zuordnungs Sequenznummer des Speicherblocks ausgefüllt wird, oder 0 (null), wenn Sie keinen aktuell aktiven Speicherblock darstellt.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Speicherblock derzeit zugeordnet ist und die Länge richtig ist. andernfalls 0.

### <a name="remarks"></a>Hinweise

Außerdem wird die angegebene Größe anhand der ursprünglich zugeordneten Größe überprüft. Wenn die Funktion einen Wert ungleich 0 (null) zurückgibt, wird die Zuordnungs Sequenznummer in *plRequestNumber*zurückgegeben. Diese Zahl gibt die Reihenfolge an, in der der Block relativ zu allen anderen **neuen** Zuordnungen zugeordnet wurde.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#27](../../mfc/codesnippet/cpp/diagnostic-services_13.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxisvalidaddress"></a>  AfxIsValidAddress

Testet jede Speicheradresse, um sicherzustellen, dass Sie vollständig im Speicherbereich des Programms enthalten ist.

```
BOOL AfxIsValidAddress(
    const void* lp,
    UINT nBytes,
    BOOL bReadWrite = TRUE);
```

### <a name="parameters"></a>Parameter

*lp*<br/>
Zeigt auf die zu testende Speicheradresse.

*nBytes*<br/>
Enthält die Anzahl der zu testenden Arbeitsspeicher bytes.

*bReadWrite*<br/>
Gibt an, ob der Speicher sowohl zum Lesen als auch zum Schreiben (true) oder zum Lesen (false) dient.

### <a name="return-value"></a>Rückgabewert

In Debugbuilds ein Wert ungleich 0 (null), wenn der angegebene Speicherblock vollständig im Speicherbereich des Programms enthalten ist. andernfalls 0.

Bei nicht-Debugbuilds ungleich 0 (null), wenn die *LP* nicht NULL ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Adresse ist nicht auf von **New**zugewiesene Blöcke beschränkt.

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
Der zu überprüfende Zeiger.

*nLength*<br/>
Gibt die Länge der zu testenden Zeichenfolge in Bytes an. Der Wert-1 gibt an, dass die Zeichenfolge mit NULL endet.

### <a name="return-value"></a>Rückgabewert

In Debugbuilds, nicht NULL, wenn der angegebene Zeiger auf eine Zeichenfolge der angegebenen Größe zeigt. andernfalls 0.

Bei nicht-Debugbuilds ungleich 0 (null), wenn *lpsz* nicht NULL ist; andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#29](../../mfc/codesnippet/cpp/diagnostic-services_15.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxsetallochook"></a>  AfxSetAllocHook

Legt einen Hook fest, der den Aufruf der angegebenen Funktion vor dem Zuordnen der einzelnen Speicherblöcke ermöglicht.

```
AFX_ALLOC_HOOK AfxSetAllocHook(AFX_ALLOC_HOOK pfnAllocHook);
```

### <a name="parameters"></a>Parameter

*pfnAllocHook*<br/>
Gibt den Namen der aufzurufenden Funktion an. Weitere Informationen finden Sie in den Hinweisen zum Prototyp einer Zuordnungs Funktion.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn Sie die Zuordnung zulassen möchten. andernfalls 0.

### <a name="remarks"></a>Hinweise

Der Microsoft Foundation Class-Bibliothek Debug-Memory-Allocator kann eine benutzerdefinierte Hookfunktion aufgerufen werden, um dem Benutzer zu ermöglichen, eine Speicher Belegung zu überwachen und zu steuern, ob die Zuordnung zulässig ist. Zuordnungs-Hook-Funktionen sind wie folgt prototyptypisiert:

**Bool afxapi-Zuweisung (size_t** `nSize` **, bool** `bObject` **, Long** `lRequestNumber` **);**

*nSize*<br/>
Die Größe der vorgeschlagenen Speicher Belegung.

*bObject*<br/>
TRUE, wenn die Zuordnung für ein `CObject`von abgeleitetes Objekt gilt; andernfalls false.

*lRequestNumber*<br/>
Die Sequenznummer der Speicher Belegung.

Beachten Sie, dass die afxapi-Aufruf Konvention impliziert, dass der aufgerufene die Parameter aus dem Stapel entfernen muss.

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxdoforallclasses"></a>  AfxDoForAllClasses

Ruft die angegebene Iterations Funktion für alle serialisierbaren `CObject`abgeleiteten Klassen im Speicherbereich der Anwendung auf.

```
void
AFXAPI AfxDoForAllClasses(
    void (* pfn)(const CRuntimeClass* pClass, void* pContext),
    void* pContext);
```

### <a name="parameters"></a>Parameter

*pfn*<br/>
Verweist auf eine Iterations Funktion, die für jede Klasse aufgerufen werden soll. Die Funktionsargumente sind ein Zeiger auf ein `CRuntimeClass` -Objekt und ein void-Zeiger auf zusätzliche Daten, die der Aufrufer für die Funktion bereitstellt.

*pContext*<br/>
Zeigt auf optionale Daten, die der Aufrufer für die Iterations Funktion bereitstellen kann. Dieser Zeiger kann NULL sein.

### <a name="remarks"></a>Hinweise

Serialisierbare `CObject`abgeleitete Klassen sind Klassen, die mithilfe des DECLARE_SERIAL-Makros abgeleitet werden. Der Zeiger, der in `AfxDoForAllClasses` *pContext* an übergeben wird, wird jedes Mal an die angegebene Iterations Funktion übergeben, wenn er aufgerufen wird.

> [!NOTE]
>  Diese Funktion kann nur in der Debugversion von MFC verwendet werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#113](../../mfc/codesnippet/cpp/diagnostic-services_16.cpp)]

[!code-cpp[NVC_MFCCollections#114](../../mfc/codesnippet/cpp/diagnostic-services_17.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="afxdoforallobjects"></a>  AfxDoForAllObjects

Führt die angegebene Iterations Funktion für alle von abgeleiteten `CObject` Objekte aus, die mit **New**zugeordnet wurden.

```
void AfxDoForAllObjects(
    void (* pfn)(CObject* pObject, void* pContext),
    void* pContext);
```

### <a name="parameters"></a>Parameter

*pfn*<br/>
Verweist auf eine Iterations Funktion, die für jedes-Objekt ausgeführt werden soll. Die Funktionsargumente sind ein Zeiger auf einen `CObject` und ein void-Zeiger auf zusätzliche Daten, die der Aufrufer für die Funktion bereitstellt.

*pContext*<br/>
Zeigt auf optionale Daten, die der Aufrufer für die Iterations Funktion bereitstellen kann. Dieser Zeiger kann NULL sein.

### <a name="remarks"></a>Hinweise

Stapel-, globale oder eingebettete Objekte werden nicht aufgezählt. Der Zeiger, `AfxDoForAllObjects` der an in *pContext* übergeben wird, wird jedes Mal, wenn er aufgerufen wird, an die angegebene Iterations Funktion übergeben.

> [!NOTE]
>  Diese Funktion kann nur in der Debugversion von MFC verwendet werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#115](../../mfc/codesnippet/cpp/diagnostic-services_18.cpp)]

[!code-cpp[NVC_MFCCollections#116](../../mfc/codesnippet/cpp/diagnostic-services_19.cpp)]

## <a name="see-also"></a>Siehe auch

[Makros und Globals](mfc-macros-and-globals.md)<br/>
[CObject::D UMP](cobject-class.md#dump)
