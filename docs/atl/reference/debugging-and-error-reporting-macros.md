---
title: Debugging-und Fehlerberichterstattungs-Makros
ms.date: 05/06/2019
f1_keywords:
- atldef/ATL::_ATL_DEBUG_INTERFACES
- atldef/ATL::_ATL_DEBUG_QI
- atldef/ATL::ATLASSERT
- afx/ATL::ATLENSURE
- atltrace/ATL::ATLTRACENOTIMPL
- atltrace/ATL::ATLTRACE
helpviewer_keywords:
- macros, error reporting
ms.assetid: 4da9b87f-ec5c-4a32-ab93-637780909b9d
ms.openlocfilehash: b666ba3debe164118c9b40b90313646592b04876
ms.sourcegitcommit: bf724dfc639b16d5410fab72183f8e6b781338bc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71062042"
---
# <a name="debugging-and-error-reporting-macros"></a>Debugging-und Fehlerberichterstattungs-Makros

Diese Makros bieten nützliche Debugging-und Ablauf Verfolgungs Funktionen.

|||
|-|-|
|[_ATL_DEBUG_INTERFACES](#_atl_debug_interfaces)|Schreibt im Ausgabefenster alle Schnittstellen Verluste, die erkannt werden, wenn `_Module.Term` aufgerufen wird.|
|[_ATL_DEBUG_QI](#_atl_debug_qi)|Schreibt alle Aufrufe von `QueryInterface` in das Ausgabefenster.|
|[ATLASSERT](#atlassert)|Führt die gleiche Funktionalität wie das [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) -Makro in der C-Lauf Zeit Bibliothek aus.|
|[ATLSICHER](#atlensure)|Führt die Parameter Validierung aus. Bei `AtlThrow` Bedarf anrufen|
|[ATLTRACENOTIMPL](#atltracenotimpl)|Sendet eine Meldung an das dumpgerät, dass die angegebene Funktion nicht implementiert ist.|
|[ATLTRACE](#atltrace)|Meldet Warnungen an ein Ausgabegerät, z. b. das Debugger-Fenster, gemäß den ermittelten Flags und Ebenen. Aus Gründen der Abwärtskompatibilität eingeschlossen.|
|[ATLTRACE2](#atltrace2)|Meldet Warnungen an ein Ausgabegerät, z. b. das Debugger-Fenster, gemäß den ermittelten Flags und Ebenen.|

##  <a name="_atl_debug_interfaces"></a>_ATL_DEBUG_INTERFACES

Definieren Sie dieses Makro, bevor Sie ATL-Header Dateien einschließen `AddRef` , `Release` um alle zu verfolgen, und rufen Sie die Schnittstellen der Komponenten an das Ausgabefenster an.

```
#define _ATL_DEBUG_INTERFACES
```

### <a name="remarks"></a>Hinweise

Die Ausgabe der Ablauf Verfolgung wird wie unten dargestellt angezeigt:

`ATL: QIThunk - 2008         AddRef  :   Object = 0x00d81ba0   Refcount = 1   CBug - IBug`

Der erste Teil jeder Ablauf Verfolgung ist immer `ATL: QIThunk`. Next ist ein Wert, der den bestimmten *Schnittstellen Thunk* identifiziert, der verwendet wird. Ein Schnittstellen Thunk ist ein Objekt, das verwendet wird, um einen Verweis Zähler beizubehalten und die hier verwendete Ablauf Verfolgungs Funktion bereitzustellen. Ein neuer Schnittstellen Thunk wird bei jedem Aufruf von erstellt `QueryInterface` , außer bei Anforderungen für `IUnknown` die-Schnittstelle (in diesem Fall wird jedes Mal derselbe Thunk zurückgegeben, um die com-Identitäts Regeln einzuhalten).

Als nächstes sehen `AddRef` `Release` Sie, welche Methode aufgerufen wurde. Danach sehen Sie einen Wert, der das Objekt identifiziert, dessen Verweis Zähler für die Schnittstelle geändert wurde. Der Wert, der verfolgt wird, ist der **this** -Zeiger des-Objekts.

Der Verweis Zähler, der nachverfolgt wird, ist der Verweis Zähler für diesen `AddRef` Thunk, nachdem oder `Release` aufgerufen wurde. Beachten Sie, dass dieser Verweis Zähler möglicherweise nicht mit dem Verweis Zähler für das Objekt identisch ist. Jeder Thunk behält seinen eigenen Verweis Zähler, um Sie bei der vollständigen Einhaltung der Regeln für die Verweis Zählung von com zu unterstützen.

Die letzten Informationen, die nachverfolgt werden, sind der Name des-Objekts und die-Schnitt `AddRef` Stelle `Release` , die vom-oder-Rückruf betroffen sind.

Alle Schnittstellen Lecks, die erkannt werden, wenn der Server heruntergefahren `_Module.Term` und aufgerufen wird, werden wie folgt protokolliert:

`ATL: QIThunk - 2005         LEAK    :   Object = 0x00d81ca0   Refcount = 1   MaxRefCount = 1   CBug - IBug`

Die Informationen, die hier bereitgestellt werden, werden direkt den Informationen in den vorherigen Ablauf Verfolgungs Anweisungen zugeordnet, damit Sie die Verweis Zähler während der gesamten Lebensdauer eines Schnittstellen Thunk untersuchen können. Außerdem erhalten Sie einen Hinweis auf den maximalen Verweis Zähler für diesen Schnittstellen Thunk.

> [!NOTE]
> _ATL_DEBUG_INTERFACES kann in Einzelhandels Builds verwendet werden.

##  <a name="_atl_debug_qi"></a>  _ATL_DEBUG_QI

Schreibt alle Aufrufe von `QueryInterface` in das Ausgabefenster.

```
#define _ATL_DEBUG_QI
```

### <a name="remarks"></a>Hinweise

Wenn beim Aufrufen von `QueryInterface` ein Fehler aufgetreten ist, wird im Ausgabefenster Folgendes angezeigt:

*Schnittstellen Name* - `failed`

##  <a name="atlassert"></a>ATLASSERT

Das ATLASSERT-Makro führt die gleiche Funktionalität wie das [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) -Makro in der C-Lauf Zeit Bibliothek aus.

```
ATLASSERT(booleanExpression);
```

### <a name="parameters"></a>Parameter

*booleanExpression*<br/>
Ausdruck (einschließlich Zeiger), der als ungleich 0 (null) oder 0 ausgewertet wird.

### <a name="remarks"></a>Hinweise

In Debugbuilds wertet ATLASSERT " *booleanExpression* " aus und generiert einen Debugbericht, wenn das Ergebnis "false" ist.

## <a name="requirements"></a>Anforderungen

**Header:** atldef. h

##  <a name="atlensure"></a>ATLSICHER

Dieses Makro wird verwendet, um Parameter zu überprüfen, die an eine Funktion geleitet werden.

```
ATLENSURE(booleanExpression);
ATLENSURE_THROW(booleanExpression, hr);
```

### <a name="parameters"></a>Parameter

*booleanExpression*<br/>
Gibt einen booleschen Ausdruck an, der getestet werden soll.

*hr*<br/>
Gibt einen Fehlercode an, der zurückgegeben werden soll.

### <a name="remarks"></a>Hinweise

Diese Makros bieten einen Mechanismus zum erkennen und Benachrichtigen des Benutzers über eine falsche Parameter Verwendung.

Das-Makro ruft ATLASSERT auf und gibt an, `AtlThrow`ob die Bedingung Aufrufe fehlschlägt.

Im atlsicher-Fall `AtlThrow` wird mit E_FAIL aufgerufen.

Im Fall `AtlThrow` von ATLENSURE_THROW wird mit dem angegebenen HRESULT aufgerufen.

Der Unterschied zwischen atlsicher und ATLASSERT besteht darin, dass ATL-sicher eine Ausnahme in Releasebuilds sowie in Debugbuilds auslöst.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#108](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_1.cpp)]

## <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="atltracenotimpl"></a>ATLTRACENOTIMPL

In Debugbuilds von ATL sendet die Zeichenfolge " *funcname* ist nicht implementiert" an das dumpgerät und gibt E_NOTIMPL zurück.

```
ATLTRACENOTIMPL(funcname);
```

### <a name="parameters"></a>Parameter

*funcname*<br/>
in Eine Zeichenfolge, die den Namen der nicht implementierten Funktion enthält.

### <a name="remarks"></a>Hinweise

Gibt in Releasebuilds einfach E_NOTIMPL zurück.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#127](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_2.cpp)]

## <a name="requirements"></a>Anforderungen

**Header:** ATLTRACE. h

##  <a name="atltrace"></a>ATLTRACE

Meldet Warnungen an ein Ausgabegerät, z. b. das Debugger-Fenster, gemäß den ermittelten Flags und Ebenen. Aus Gründen der Abwärtskompatibilität eingeschlossen.

```
ATLTRACE(exp);

ATLTRACE(
    DWORD category,
    UINT  level,
    LPCSTR lpszFormat, ...);
```

### <a name="parameters"></a>Parameter

*exp*<br/>
in Die Zeichenfolge und Variablen, die an das Ausgabefenster oder an eine beliebige Anwendung gesendet werden, die diese Nachrichten abfängt

*category*<br/>
in Typ des Ereignisses oder der Methode, für die ein Bericht ausgegeben werden soll. Eine Liste der Kategorien finden Sie in den hinweisen.

*level*<br/>
in Die Ebene der Ablauf Verfolgung, die gemeldet werden soll. Weitere Informationen finden Sie in den hinweisen.

*lpszFormat*<br/>
in Die formatierte Zeichenfolge, die an das dumpgerät gesendet werden soll.

### <a name="remarks"></a>Hinweise

Eine Beschreibung von ATLTRACE finden Sie unter [ATLTRACE2](#atltrace2) . ATLTRACE und ATLTRACE2 haben das gleiche Verhalten, ATLTRACE ist aus Gründen der Abwärtskompatibilität eingeschlossen.

##  <a name="atltrace2"></a>ATLTRACE2

Meldet Warnungen an ein Ausgabegerät, z. b. das Debugger-Fenster, gemäß den ermittelten Flags und Ebenen.

```
ATLTRACE2(exp);

ATLTRACE2(
    DWORD category,
    UINT level,
    LPCSTR lpszFormat,  ...);
```

### <a name="parameters"></a>Parameter

*exp*<br/>
in Die Zeichenfolge, die an das Ausgabefenster oder eine beliebige Anwendung gesendet wird, die diese Nachrichten abfängt.

*category*<br/>
in Typ des Ereignisses oder der Methode, für die ein Bericht ausgegeben werden soll. Eine Liste der Kategorien finden Sie in den hinweisen.

*level*<br/>
in Die Ebene der Ablauf Verfolgung, die gemeldet werden soll. Weitere Informationen finden Sie in den hinweisen.

*lpszFormat*<br/>
in Die `printf`Format Zeichenfolge im Format, mit der eine Zeichenfolge erstellt wird, die an das dumpgerät gesendet werden soll.

### <a name="remarks"></a>Hinweise

Die Kurzform von ATLTRACE2 schreibt eine Zeichenfolge in das Ausgabefenster des Debuggers. Die zweite Form von ATLTRACE2 schreibt auch die Ausgabe in das Ausgabefenster des Debuggers, unterliegt jedoch den Einstellungen des ATL/MFC-Ablauf Verfolgungs Tools (siehe [AtlTraceTool-Beispiel](../../overview/visual-cpp-samples.md)). Wenn Sie z. b. *Level* auf 4 festlegen und das ATL/MFC-Ablaufverfolgungs-Tool auf Level 0 festgelegt ist, wird die Meldung nicht angezeigt. die *Ebene* kann 0, 1, 2, 3 oder 4 sein. Der Standardwert ist 0 und meldet nur die schwerwiegendsten Probleme.

Der Parameter *Category* listet die festzulegenden Ablaufverfolgungsflags auf. Diese Flags entsprechen den Methoden Typen, für die Sie Berichte schreiben möchten. Die folgenden Tabellen enthalten die gültigen Ablaufverfolgungsflags, die Sie für den *Category* -Parameter verwenden können.

### <a name="atl-trace-flags"></a>ATL-Ablauf Verfolgungs Flags

|ATL-Kategorie|Beschreibung|
|------------------|-----------------|
|`atlTraceGeneral`|Berichte zu allen ATL-Anwendungen. Der Standardwert.|
|`atlTraceCOM`|Berichte zu com-Methoden.|
|`atlTraceQI`|Berichte zu QueryInterface-aufrufen.|
|`atlTraceRegistrar`|Meldet die Registrierung von-Objekten.|
|`atlTraceRefcount`|Meldet über das Ändern der Verweis Anzahl.|
|`atlTraceWindowing`|Berichte zu Windows-Methoden Beispielsweise meldet eine ungültige Meldungs Zuordnungs-ID.|
|`atlTraceControls`|Berichte zu Steuerelementen; Beispielsweise meldet, wenn ein Steuerelement oder sein Fenster zerstört wird.|
|`atlTraceHosting`|Meldet das Hosting von Nachrichten. Beispielsweise meldet, wenn ein Client in einem Container aktiviert wird.|
|`atlTraceDBClient`|Berichte über OLE DB consumervorlage Wenn z. b. beim Aufrufen von GetData ein Fehler auftritt, kann die Ausgabe das HRESULT enthalten.|
|`atlTraceDBProvider`|Berichte über OLE DB Anbieter Vorlage Beispielsweise meldet, ob die Erstellung einer Spalte fehlgeschlagen ist.|
|`atlTraceSnapin`|Berichte für die MMC-Snap-in-Anwendung.|
|`atlTraceNotImpl`|Meldet, dass die festgestellte Funktion nicht implementiert ist.|
|`atlTraceAllocation`|Meldet die von den speicherdebuggingtools in atldbgmem. h gedruckten Nachrichten.|

### <a name="mfc-trace-flags"></a>MFC-Trace-Flags

|MFC-Kategorie|Beschreibung|
|------------------|-----------------|
|`traceAppMsg`|Allgemeine MFC-Nachrichten. Wird immer empfohlen.|
|`traceDumpContext`|Nachrichten aus [CDumpContext](../../mfc/reference/cdumpcontext-class.md).|
|`traceWinMsg`|Nachrichten aus dem Nachrichten Behandlungs Code von MFC.|
|`traceMemory`|Nachrichten aus dem Speicherverwaltungscode von MFC.|
|`traceCmdRouting`|Nachrichten aus dem Windows-Befehls Weiterleitungs Code von MFC.|
|`traceHtml`|Nachrichten von der MFC-Unterstützung des DHTML-Dialogs.|
|`traceSocket`|Nachrichten von der MFC-Socketunterstützung.|
|`traceOle`|Nachrichten von der MFC-OLE-Unterstützung.|
|`traceDatabase`|Nachrichten von der MFC-Datenbankunterstützung.|
|`traceInternet`|Nachrichten von der MFC-Internet Unterstützung.|

Um eine benutzerdefinierte Ablauf Verfolgungs Kategorie zu deklarieren, deklarieren `CTraceCategory` Sie eine globale Instanz der-Klasse wie folgt:

[!code-cpp[NVC_ATL_Utilities#109](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_3.cpp)]

Der Kategoriename MY_CATEGORY in diesem Beispiel ist der Name, den Sie für den *Category* -Parameter angeben. Der erste Parameter ist der Kategoriename, der im ATL/MFC-Ablauf Verfolgungs Tool angezeigt wird. Der zweite Parameter ist die Standard Ablauf Verfolgungs Ebene. Dieser Parameter ist optional, und die Standard Ablauf Verfolgungs Ebene ist 0.

So verwenden Sie eine benutzerdefinierte Kategorie:

[!code-cpp[NVC_ATL_Utilities#110](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_4.cpp)]

Wenn Sie angeben möchten, dass die Ablauf Verfolgungs Meldungen gefiltert werden sollen, fügen Sie vor der `#include <atlbase.h>` -Anweisung Definitionen für diese Makros in stdafx. h ein.

Alternativ können Sie den Filter in den Präprozessordirektiven im Dialogfeld **Eigenschaften Seiten** festlegen. Klicken Sie auf die Registerkarte **Präprozessor** , und fügen Sie dann den globalen in das Bearbeitungsfeld **Präprozessordefinitionen** ein.

Atlbase. h enthält Standarddefinitionen der ATLTRACE2-Makros. diese Definitionen werden verwendet, wenn Sie diese Symbole nicht vor der Verarbeitung von "atlbase. h" definieren.

In Releasebuilds kompiliert `(void) 0`ATLTRACE2 in.

ATLTRACE2 schränkt die Inhalte der Zeichenfolge ein, die nach der Formatierung nicht mehr als 1023 Zeichen an das dumpgerät gesendet werden soll.

ATLTRACE und ATLTRACE2 haben das gleiche Verhalten, ATLTRACE ist aus Gründen der Abwärtskompatibilität eingeschlossen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#111](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_5.cpp)]

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)<br/>
[Debuggen und globale Funktionen für die Fehlerberichterstattung](../../atl/reference/debugging-and-error-reporting-global-functions.md)
