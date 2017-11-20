---
title: Debuggen und die Fehlerberichterstattung Makros | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atldef/ATL::_ATL_DEBUG_INTERFACES
- atldef/ATL::_ATL_DEBUG_QI
- atldef/ATL::ATLASSERT
- afx/ATL::ATLENSURE
- atltrace/ATL::ATLTRACENOTIMPL
- atltrace/ATL::ATLTRACE
dev_langs: C++
helpviewer_keywords: macros, error reporting
ms.assetid: 4da9b87f-ec5c-4a32-ab93-637780909b9d
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e14ffb58ba19c6c3c8d3e59181a045532f5cfb92
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="debugging-and-error-reporting-macros"></a>Debuggen und die Fehlerberichterstattung-Makros
Diese Makros stellen nützlich, Debuggen und Ablaufverfolgung Funktionen bereit.  
  
|||  
|-|-|  
|[_ATL_DEBUG_INTERFACES](#_atl_debug_interfaces)|Schreibt, in das Ausgabefenster einer beliebigen Schnittstelle Speicherverluste, die erkannt werden, wenn `_Module.Term` aufgerufen wird.|  
|[_ATL_DEBUG_QI](#_atl_debug_qi)|Schreibt alle Aufrufe an `QueryInterface` im Ausgabefenster.|  
|[ATLASSERT](#atlassert)|Führt die gleiche Funktionalität wie die [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) Makro wurde in der C-Laufzeitbibliothek gefunden.|  
|[ATLENSURE](#atlensure)|Parameter überprüft. Rufen Sie `AtlThrow` bei Bedarf|  
|[ATLTRACENOTIMPL](#atltracenotimpl)|Sendet eine Nachricht auf das Sicherungsmedium, dass die angegebene Funktion ist nicht implementiert.|  
|[ATLTRACE](#alttrace)|Gibt Warnungen, um ein Ausgabegerät, z. B. das Debuggerfenster, entsprechend der angegebenen Flags und Ebenen. Aus Gründen der Abwärtskompatibilität.|  
|[ATLTRACE2](#atltrace2)|Gibt Warnungen, um ein Ausgabegerät, z. B. das Debuggerfenster, entsprechend der angegebenen Flags und Ebenen.|  
  
##  <a name="_atl_debug_interfaces"></a>_ATL_DEBUG_INTERFACES  
 Dieses Makro zu definieren, bevor Sie alle ATL-Headerdateien, um alle Ablaufverfolgungsinformationen einschließlich `AddRef` und **Version** auf Ihre Komponenten Schnittstellen, um das Fenster "Ausgabe" aufruft.  
  
```
#define _ATL_DEBUG_INTERFACES
```  
  
### <a name="remarks"></a>Hinweise  
 Die Trace-Ausgabe wird angezeigt, wie unten dargestellt:  
  
 `ATL: QIThunk - 2008         AddRef  :   Object = 0x00d81ba0   Refcount = 1   CBug - IBug`  
  
 Der erste Teil der einzelnen ablaufverfolgungen werden immer `ATL: QIThunk`. Als Nächstes wird ein Wert identifiziert die spezielle *Schnittstelle Thunk* verwendet wird. Eine Schnittstelle Thunk handelt es sich um ein Objekt, das zum Verwalten einer Verweisanzahl und bieten die Möglichkeit Ablaufverfolgung, die hier verwendete verwendet. Erstellt ein neue Schnittstelle Thunk bei jedem Aufruf von `QueryInterface` mit Ausnahme von Anforderungen für die **IUnknown** -Schnittstelle (in diesem Fall der gleiche Thunk Rückgabewert jedes Mal zur Einhaltung des COM-Identity-Regeln).  
  
 Als Nächstes sehen Sie `AddRef` oder **Version** , der angibt, welche Methode aufgerufen wurde. Danach sehen Sie einen Wert zur Identifizierung des Objekts, dessen Verweiszähler für Schnittstellen geändert wurde. Der Wert wird nachverfolgt, ist die **dies** Zeiger des Objekts.  
  
 Der Verweiszähler, dessen Ablauf verfolgt wird, wird der Verweiszähler auf diesem Thunk nach `AddRef` oder **Version** aufgerufen wurde. Beachten Sie, dass diese Verweiszähler dieser Planergruppe den Verweiszähler für das Objekt möglicherweise nicht übereinstimmt. Jede Thunk verwaltet einen eigenen Verweiszähler um lassen sich vollständig von COM-verweiszählung Regeln entsprechen.  
  
 Die endgültige Information wird nachverfolgt, ist der Name des Objekts und die Schnittstelle von betroffen sind der `AddRef` oder **Version** aufrufen.  
  
 Jede Schnittstelle prüfen auf Speicherverluste, die erkannt werden, wenn der Server heruntergefahren und `_Module.Term` aufrufen angemeldet sein, wie folgt:  
  
 `ATL: QIThunk - 2005         LEAK    :   Object = 0x00d81ca0   Refcount = 1   MaxRefCount = 1   CBug - IBug`  
  
 Hier bereitgestellten Zuordnungen direkt mit den Angaben in der vorherigen ablaufverfolgungsanweisungen Informationen, damit Sie prüfen können, den Verweiszähler während der gesamten Lebensdauer einer Schnittstelle Thunk. Darüber hinaus erhalten Sie einen Überblick über die Anzahl der maximal zulässige Verweisdaten auf diese Schnittstelle Thunk.  
  
> [!NOTE]
> `_ATL_DEBUG_INTERFACES`kann in Verkaufsversionen verwendet werden.  
  
##  <a name="_atl_debug_qi"></a>_ATL_DEBUG_QI  
 Schreibt alle Aufrufe an `QueryInterface` im Ausgabefenster.  
  
```
#define _ATL_DEBUG_QI
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Aufruf von `QueryInterface` fehlgeschlagen ist, wird das Fenster "Ausgabe" angezeigt:  
  
 *Schnittstellenname* - `failed`  
  
##  <a name="atlassert"></a>ATLASSERT  
 Die `ATLASSERT` Makro führt die gleiche Funktionalität wie die [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) Makro wurde in der C-Laufzeitbibliothek gefunden.  
  
```
ATLASSERT(booleanExpression);
```  
  
### <a name="parameters"></a>Parameter  
 `booleanExpression`  
 Ausdruck (einschließlich Zeiger), der ungleich NULL oder 0 ergibt.  
  
### <a name="remarks"></a>Hinweise  
 Debug-Builds `ATLASSERT` ergibt `booleanExpression` und erzeugt einen Debugbericht, wenn das Ergebnis "false" ist.  

## <a name="requirements"></a>Anforderungen  
 **Header:** atldef.h  
    
##  <a name="atlensure"></a>ATLENSURE  
 Dieses Makro wird verwendet, um an eine Funktion übergebenen Parameter zu überprüfen.  
  
```
ATLENSURE(booleanExpression);
ATLENSURE_THROW(booleanExpression, hr);
```  
  
### <a name="parameters"></a>Parameter  
 `booleanExpression`  
 Gibt einen booleschen Ausdruck, der darauf getestet werden.  
  
 `hr`  
 Gibt den Fehlercode zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Makros bieten einen Mechanismus zum Erkennen und dem Benutzer falsche Parameterverwendung.  
  
 Die Makro-Aufrufe `ATLASSERT` und wenn die Bedingung schlägt, Aufrufe fehl `AtlThrow`.  
  
 In der **ATLENSURE** Fall `AtlThrow` mit E_FAIL aufgerufen wird.  
  
 In der **ATLENSURE_THROW** Fall `AtlThrow` mit dem angegebenen HRESULT aufgerufen wird.  
  
 Der Unterschied zwischen **ATLENSURE** und `ATLASSERT` handelt, **ATLENSURE** löst eine Ausnahme in Version ebenfalls, wie in der Debug-Builds erstellt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#108](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_1.cpp)]  

## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  

##  <a name="atltracenotimpl"></a>ATLTRACENOTIMPL  
 In Debugbuilds von ATL, sendet die Zeichenfolge " `funcname` ist nicht implementiert" auf das Sicherungsmedium und gibt **E_NOTIMPL**.  
  
```
ATLTRACENOTIMPL(funcname);
```  
  
### <a name="parameters"></a>Parameter  
 `funcname`  
 [in] Eine Zeichenfolge, die mit dem Namen der Funktion, die nicht implementiert ist.  
  
### <a name="remarks"></a>Hinweise  
 Einfach in Releasebuilds zurückgibt **E_NOTIMPL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#127](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_2.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atltrace.h 

##  <a name="atltrace"></a>ATLTRACE
 Gibt Warnungen, um ein Ausgabegerät, z. B. das Debuggerfenster, entsprechend der angegebenen Flags und Ebenen. Aus Gründen der Abwärtskompatibilität.  
  
```
ATLTRACE(exp);

ATLTRACE(  
    DWORD category,
    UINT  level,
    LPCSTR lpszFormat, ...);
```  
  
### <a name="parameters"></a>Parameter  
 `exp`  
 [in] Die Zeichenfolge und die Variablen an das Ausgabefenster von Visual C++ oder einer beliebigen Anwendung, die diese Nachrichten traps zu senden.  
  
 `category`  
 [in] Der Typ eines Ereignisses oder einer Methode auf dem Bericht. Finden Sie unter den Hinweisen für eine Liste der Kategorien.  
  
 `level`  
 [in] Die Ebene der Ablaufverfolgung zum Bericht. Finden Sie unter den Hinweisen für Details.  
  
 `lpszFormat`  
 [in] Die formatierte Zeichenfolge das Sicherungsgerät an.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [ATLTRACE2](#atltrace2) eine Beschreibung der **ATLTRACE**. **ATLTRACE** und `ATLTRACE2` weisen das gleiche Verhalten **ATLTRACE** wird aus Gründen der Abwärtskompatibilität.  
  
##  <a name="atltrace2"></a>ATLTRACE2  
 Gibt Warnungen, um ein Ausgabegerät, z. B. das Debuggerfenster, entsprechend der angegebenen Flags und Ebenen.  
  
```
ATLTRACE2(exp);

ATLTRACE2(
    DWORD category,
    UINT level,
    LPCSTRlpszFormat,  ...);
```  
  
### <a name="parameters"></a>Parameter  
 `exp`  
 [in] Die Zeichenfolge zum Senden an das Ausgabefenster von Visual C++ oder einer beliebigen Anwendung, die diese Nachrichten aufgefangen.  
  
 `category`  
 [in] Der Typ eines Ereignisses oder einer Methode auf dem Bericht. Finden Sie unter den Hinweisen für eine Liste der Kategorien.  
  
 `level`  
 [in] Die Ebene der Ablaufverfolgung zum Bericht. Finden Sie unter den Hinweisen für Details.  
  
 `lpszFormat`  
 [in] Die `printf`-Stil Formatzeichenfolge, mit der eine Zeichenfolge zum Senden an das Sicherungsmedium zu erstellen.  
  
### <a name="remarks"></a>Hinweise  
 Die Kurzform der `ATLTRACE2` schreibt eine Zeichenfolge, die der Debugger die Fenster Ausgabe. Die zweite Form der `ATLTRACE2` auch schreibt die Ausgabe in der Debugger-Fenster "Ausgabe", aber die Einstellungen der ATL-/MFC-Ablaufverfolgungsprogramm unterliegt (finden Sie unter [ATLTraceTool-Beispiel](../../visual-cpp-samples.md)). Wenn Sie festlegen, z. B. `level` 4 und die ATL/MFC-Ablaufverfolgungsprogramm auf Ebene 0, werden Sie nicht die Meldung angezeigt. *Ebene* kann 0, 1, 2, 3 oder 4 sein. Standardmäßig 0 (null) gibt nur die schwerwiegendsten Probleme.  
  
 Die `category` Parameterlisten Ablaufverfolgungsflags festgelegt. Diese Flags entsprechen den Typen der Methoden, die für die Sie einen Bericht erstellen möchten. Die folgenden Tabellen enthalten die gültigen Ablaufverfolgungsflags Sie für können die `category` Parameter.  
  
### <a name="atl-trace-flags"></a>ATL-Ablaufverfolgungsflags  
  
|ATL-Kategorie|Beschreibung|  
|------------------|-----------------|  
|`atlTraceGeneral`|Meldet alle ATL-Anwendungen. Der Standardwert.|  
|`atlTraceCOM`|Enthält Angaben zur COM-Methoden.|  
|`atlTraceQI`|Enthält Angaben zur QueryInterface-Aufrufe.|  
|`atlTraceRegistrar`|Berichte für die Registrierung von Objekten.|  
|`atlTraceRefcount`|Berichte zum Ändern der Verweiszähler dieser Planergruppe.|  
|`atlTraceWindowing`|Berichten auf Windows-Methoden. Beispielsweise gibt eine ungültige Nachricht Karten-ID.|  
|`atlTraceControls`|Berichte für Steuerelemente Beispielsweise wird berichtet, wenn ein Steuerelement oder das Fenster zerstört wird.|  
|`atlTraceHosting`|Berichte, die Meldungen hosten; Beispielsweise wird berichtet, wenn ein Client in einem Container aktiviert ist.|  
|`atlTraceDBClient`|Berichte über OLE DB-Consumervorlagen; Beispielsweise kann bei einem Aufruf GetData ein Fehler auftritt, die Ausgabe enthalten HRESULT.|  
|`atlTraceDBProvider`|Berichten auf die Vorlage für OLE DB-Anbieter. gibt z. B., wenn Fehler beim Erstellen einer Spalte.|  
|`atlTraceSnapin`|Berichte können zur MMC-Snap-in-Anwendung.|  
|`atlTraceNotImpl`|Gibt an, dass die angegebene Funktion ist nicht implementiert.|  
|**atlTraceAllocation**|Gibt die Nachrichten, die durch den Arbeitsspeicher Debugtools in atldbgmem.h gedruckt.|  
  
### <a name="mfc-trace-flags"></a>MFC-Ablaufverfolgungsflags  
  
|MFC-Kategorie|Beschreibung|  
|------------------|-----------------|  
|**traceAppMsg**|Allgemeine MFC-Nachrichten. Immer empfohlen.|  
|**traceDumpContext**|Nachrichten von [CDumpContext](../../mfc/reference/cdumpcontext-class.md).|  
|**traceWinMsg**|Meldungen vom MFC Nachricht, die Verarbeitung von Code.|  
|**traceMemory**|Meldungen vom MFC Speicher-Management-Code.|  
|**traceCmdRouting**|Nachrichten von MFC Windows-Befehl routing Code.|  
|**traceHtml**|Meldungen vom MFC Unterstützung für DHTML das Dialogfeld.|  
|**traceSocket**|Meldungen vom MFC Socket-Unterstützung.|  
|**traceOle**|Meldungen vom MFC OLE-Unterstützung.|  
|**traceDatabase**|Meldungen vom MFC datenbankunterstützung.|  
|**traceInternet**|Meldungen vom MFC Unterstützung.|  
  
 Um eine benutzerdefinierte Ablaufverfolgungskategorie zu deklarieren, deklarieren Sie eine globale Instanz von der `CTraceCategory` -Klasse wie folgt:  
  
 [!code-cpp[NVC_ATL_Utilities#109](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_3.cpp)]  
  
 Der Kategoriename, `MY_CATEGORY` in diesem Beispiel wird der Name, die Sie, die angeben die `category` Parameter. Der erste Parameter ist, den Namen der Kategorie, der in den ATL-/MFC-Ablaufverfolgungsprogramm angezeigt werden. Der zweite Parameter ist der Standard-Ablaufverfolgungsebene. Dieser Parameter ist optional, und die standardmäßige Ablaufverfolgungsebene ist 0.  
  
 So verwenden Sie eine benutzerdefinierte Kategorie:  
  
 [!code-cpp[NVC_ATL_Utilities#110](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_4.cpp)]  
  
 Um anzugeben, dass Sie die Ablaufverfolgungsmeldungen filtern möchten, legen Sie Definitionen für diese Makros in "stdafx.h", bevor die `#include <atlbase.h>` Anweisung.  
  
 Alternativ können Sie den Filter festlegen, in die Präprozessordirektiven in die **Eigenschaftenseiten** (Dialogfeld). Klicken Sie auf die **Präprozessor** Registerkarte, und fügen Sie dann auf die globale in der **Präprozessordefinitionen** Eingabefeld.  
  
 Atlbase.h enthält Default-Definitionen von der `ATLTRACE2` Makros und diese Definitionen werden verwendet, wenn Sie nicht diese Symbole definieren, bevor atlbase.h verarbeitet wird.  
  
 In Releasebuilds `ATLTRACE2` kompiliert `(void) 0`.  
  
 `ATLTRACE2`Schränkt den Inhalt der Zeichenfolge, die an das Gerät Dump nicht mehr als 1023 Zeichen nach der Formatierung gesendet werden.  
  
 **ATLTRACE** und `ATLTRACE2` weisen das gleiche Verhalten **ATLTRACE** wird aus Gründen der Abwärtskompatibilität.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#111](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_5.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)   
 [Debuggen und globale Funktionen für die Fehlerberichterstattung](../../atl/reference/debugging-and-error-reporting-global-functions.md)
