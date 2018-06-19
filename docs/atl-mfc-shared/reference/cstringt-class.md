---
title: CStringT Class | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStringT
- ATLSTR/ATL::CStringT
- ATLSTR/ATL::CStringT::CStringT
- ATLSTR/ATL::CStringT::AllocSysString
- ATLSTR/ATL::CStringT::AnsiToOem
- ATLSTR/ATL::CStringT::AppendFormat
- ATLSTR/ATL::CStringT::Collate
- ATLSTR/ATL::CStringT::CollateNoCase
- ATLSTR/ATL::CStringT::Compare
- ATLSTR/ATL::CStringT::CompareNoCase
- ATLSTR/ATL::CStringT::Delete
- ATLSTR/ATL::CStringT::Find
- ATLSTR/ATL::CStringT::FindOneOf
- ATLSTR/ATL::CStringT::Format
- ATLSTR/ATL::CStringT::FormatMessage
- ATLSTR/ATL::CStringT::FormatMessageV
- ATLSTR/ATL::CStringT::FormatV
- ATLSTR/ATL::CStringT::GetEnvironmentVariable
- ATLSTR/ATL::CStringT::Insert
- ATLSTR/ATL::CStringT::Left
- ATLSTR/ATL::CStringT::LoadString
- ATLSTR/ATL::CStringT::MakeLower
- ATLSTR/ATL::CStringT::MakeReverse
- ATLSTR/ATL::CStringT::MakeUpper
- ATLSTR/ATL::CStringT::Mid
- ATLSTR/ATL::CStringT::OemToAnsi
- ATLSTR/ATL::CStringT::Remove
- ATLSTR/ATL::CStringT::Replace
- ATLSTR/ATL::CStringT::ReverseFind
- ATLSTR/ATL::CStringT::Right
- ATLSTR/ATL::CStringT::SetSysString
- ATLSTR/ATL::CStringT::SpanExcluding
- ATLSTR/ATL::CStringT::SpanIncluding
- ATLSTR/ATL::CStringT::Tokenize
- ATLSTR/ATL::CStringT::Trim
- ATLSTR/ATL::CStringT::TrimLeft
- ATLSTR/ATL::CStringT::TrimRight
- CSTRINGT/CStringT
- CSTRINGT/CStringT::CStringT
- CSTRINGT/CStringT::AllocSysString
- CSTRINGT/CStringT::AnsiToOem
- CSTRINGT/CStringT::AppendFormat
- CSTRINGT/CStringT::Collate
- CSTRINGT/CStringT::CollateNoCase
- CSTRINGT/CStringT::Compare
- CSTRINGT/CStringT::CompareNoCase
- CSTRINGT/CStringT::Delete
- CSTRINGT/CStringT::Find
- CSTRINGT/CStringT::FindOneOf
- CSTRINGT/CStringT::Format
- CSTRINGT/CStringT::FormatMessage
- CSTRINGT/CStringT::FormatMessageV
- CSTRINGT/CStringT::FormatV
- CSTRINGT/CStringT::GetEnvironmentVariable
- CSTRINGT/CStringT::Insert
- CSTRINGT/CStringT::Left
- CSTRINGT/CStringT::LoadString
- CSTRINGT/CStringT::MakeLower
- CSTRINGT/CStringT::MakeReverse
- CSTRINGT/CStringT::MakeUpper
- CSTRINGT/CStringT::Mid
- CSTRINGT/CStringT::OemToAnsi
- CSTRINGT/CStringT::Remove
- CSTRINGT/CStringT::Replace
- CSTRINGT/CStringT::ReverseFind
- CSTRINGT/CStringT::Right
- CSTRINGT/CStringT::SetSysString
- CSTRINGT/CStringT::SpanExcluding
- CSTRINGT/CStringT::SpanIncluding
- CSTRINGT/CStringT::Tokenize
- CSTRINGT/CStringT::Trim
- CSTRINGT/CStringT::TrimLeft
- CSTRINGT/CStringT::TrimRight
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], in ATL
- shared classes, CStringT
- CStringT class
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f8a66f87b3c4a2c6712a1db93f97361a25b6955
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366626"
---
# <a name="cstringt-class"></a>CStringT-Klasse
Diese Klasse stellt ein `CStringT` Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
 
template<typename BaseType, class StringTraits>  
class CStringT :   
public CSimpleStringT<BaseType,
                      _CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>
                      ::c_bIsMFCDLLTraits>  
 
```  
  
#### <a name="parameters"></a>Parameter  
 `BaseType`  
 Der Typ der Zeichenfolgenklasse. Einer der folgenden Werte ist möglich:  
  
- `char` (für ANSI-Zeichenfolgen).  
  
- `wchar_t` (für Unicode-Zeichenfolgen).  
  
- **TCHAR** (für ANSI- und Unicode-Zeichenfolgen).  
  
 `StringTraits`  
 Bestimmt, ob der Zeichenfolgenklasse benötigt Unterstützung für C-Laufzeit (CRT)-Bibliothek und unter dem Zeichenfolgenressourcen gespeichert werden. Einer der folgenden Werte ist möglich:  
  
- **StrTraitATL < Wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsCRT < Wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     Die Klasse erfordert, CRT-Unterstützung und sucht nach Ressourcenzeichenfolgen im Modul gemäß `m_hInstResource` (ein Mitglied der Anwendung Module-Klasse).  
  
- **StrTraitATL < Wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsOS < Wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     Die Klasse ist nicht erforderlich, CRT-Unterstützung und sucht nach Ressourcenzeichenfolgen im Modul gemäß `m_hInstResource` (ein Mitglied der Anwendung Module-Klasse).  
  
- **StrTraitMFC < Wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsCRT < Wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     Die Klasse erfordert CRT-Unterstützung und sucht nach Ressourcenzeichenfolgen, die mit den MFC-Suche Standardalgorithmus.  
  
- **StrTraitMFC < Wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsOS < Wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     Die Klasse erfordert keine CRT-Unterstützung und sucht nach Ressourcenzeichenfolgen, die mit den MFC-Suche Standardalgorithmus.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStringT::CStringT](#cstringt)|Erstellt eine `CStringT` Objekts auf verschiedene Weise.|  
|[CStringT:: ~ CStringT](#_dtorcstringt)|Zerstört ein `CStringT`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStringT::AllocSysString](#allocsysstring)|Ordnet eine `BSTR` aus `CStringT` Daten.|  
|[CStringT::AnsiToOem](#ansitooem)|Stellt eine direkte Konvertierung aus dem ANSI-Zeichensatz in den OEM-Zeichensatz.|  
|[CStringT::AppendFormat](#appendformat)|Fügt der formatierte Daten einer vorhandenen `CStringT` Objekt.|  
|[CStringT::Collate](#collate)|Vergleicht zwei Zeichenfolgen (Groß-/Kleinschreibung beachtet, mithilfe gebietsschemaspezifischen Informationen).|  
|[CStringT::CollateNoCase](#collatenocase)|Vergleicht zwei Zeichenfolgen (Groß-/Kleinschreibung nicht beachtet, mithilfe gebietsschemaspezifischen Informationen).|  
|[CStringT::Compare](#compare)|Vergleicht zwei Zeichenfolgen (Groß-/Kleinschreibung wird beachtet).|  
|[CStringT::CompareNoCase](#comparenocase)|Vergleicht zwei Zeichenfolgen (Groß-/Kleinschreibung beachten).|  
|[CStringT::Delete](#delete)|Löscht ein Zeichen oder Zeichen aus einer Zeichenfolge.|  
|[CStringT::Find](#find)|Sucht nach einem Zeichen oder eine Teilzeichenfolge innerhalb einer größeren Zeichenfolge.|  
|[CStringT::FindOneOf](#findoneof)|Sucht das erste übereinstimmende Zeichen aus einem Satz an.|  
|[CStringT::Format](#format)|Formatiert die Zeichenfolge als `sprintf` verfügt.|  
|[CStringT::FormatMessage](#formatmessage)|Formatiert eine Meldungszeichenfolge.|  
|[CStringT::FormatMessageV](#formatmessagev)|Formatiert eine Meldungszeichenfolge, die mit einer Liste variabler Argumente an.|  
|[CStringT::FormatV](#formatv)|Formatiert die Zeichenfolge, die mit der eine Variable Argumentliste.|  
|[CStringT::GetEnvironmentVariable](#getenvironmentvariable)|Legt die Zeichenfolge auf den Wert der angegebenen Umgebungsvariablen.|  
|[CStringT::Insert](#insert)|Fügt ein einzelnes Zeichen oder eine Teilzeichenfolge am angegebenen Index in der Zeichenfolge ein.|  
|[CStringT::Left](#left)|Extrahiert den linken Teil einer Zeichenfolge.|  
|[CStringT::LoadString](#loadstring)|Lädt ein vorhandenes `CStringT` Objekt aus einer Windows-Ressource.|  
|[CStringT::MakeLower](#makelower)|Konvertiert alle Zeichen in dieser Zeichenfolge in Kleinbuchstaben.|  
|[CStringT::MakeReverse](#makereverse)|Kehrt die Zeichenfolge an.|  
|[CStringT::MakeUpper](#makeupper)|Konvertiert alle Zeichen in dieser Zeichenfolge in Großbuchstaben.|  
|[CStringT::Mid](#mid)|Extrahiert den mittleren Teil einer Zeichenfolge.|  
|[CStringT::OemToAnsi](#oemtoansi)|Stellt eine direkte Konvertierung aus dem OEM-Zeichensatz der ANSI-Zeichensatz.|  
|[CStringT::Remove](#remove)|Entfernt einen angegebenen Zeichen aus einer Zeichenfolge.|  
|[CStringT::Replace](#replace)|Ersetzt angegebene Zeichen mit anderen Zeichen.|  
|[CStringT::ReverseFind](#reversefind)|Sucht ein Zeichen innerhalb einer größeren Zeichenfolge. beginnt am Ende.|  
|[CStringT::Right](#right)|Extrahiert den rechten Teil einer Zeichenfolge.|  
|[CStringT::SetSysString](#setsysstring)|Legt eine vorhandene `BSTR` Objekt mit Daten aus einem `CStringT` Objekt.|  
|[CStringT::SpanExcluding](#spanexcluding)|Extrahiert Zeichen aus der Zeichenfolge, beginnend mit dem ersten Zeichen, die nicht in den Satz von Zeichen, die erkennbar sind `pszCharSet`.|  
|[CStringT::SpanIncluding](#spanincluding)|Extrahiert eine Teilzeichenfolge, die nur die Zeichen in einem Satz enthält.|  
|[CStringT::Tokenize](#tokenize)|Extrahiert angegebene Token in einer Zielzeichenfolge.|  
|[CStringT::Trim](#trim)|Entfernt alle führenden und nachgestellten Leerraumzeichen aus der Zeichenfolge.|  
|[CStringT::TrimLeft](#trimleft)|Entfernt führende Leerzeichen aus der Zeichenfolge.|  
|[CStringT::TrimRight](#trimright)|Entfernt nachfolgende Leerzeichen aus der Zeichenfolge.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator =](#operator_eq)|Weist einen neuen Wert zu einem `CStringT` Objekt.|  
|[CStringT::operator +](#operator_add)|Verkettet zwei Zeichenfolgen oder ein Zeichen und eine Zeichenfolge.|  
|[CStringT::operator +=](#operator_add_eq)|Verkettet eine neue Zeichenfolge am Ende einer vorhandenen Zeichenfolge an.|  
|[CStringT::operator ==](#operator_eq_eq)|Bestimmt, ob zwei Zeichenfolgen logisch gleich sind.|  
|[CStringT::operator! =](#operator_neq)|Bestimmt, ob zwei Zeichenfolgen logisch nicht gleich sind.|  
|[CStringT::operator &lt;](#operator_lt)|Bestimmt, ob die Zeichenfolge auf der linken Seite des Operators kleiner als die Zeichenfolge auf der rechten Seite.|  
|[CStringT::operator &gt;](#operator_gt)|Bestimmt, ob die Zeichenfolge auf der linken Seite des Operators größer als die Zeichenfolge auf der rechten Seite ist.|  
|[CStringT::operator &lt;=](#operator_lt_eq)|Bestimmt, ob die Zeichenfolge auf der linken Seite des Operators kleiner als oder gleich der Zeichenfolge auf der rechten Seite ist.|  
|[CStringT::operator &gt;=](#operator_gt_eq)|Bestimmt, ob die Zeichenfolge auf der linken Seite des Operators größer als oder gleich der Zeichenfolge auf der rechten Seite ist.|  
  
## <a name="remarks"></a>Hinweise  
 `CStringT` erbt von [CSimpleStringT Klasse](../../atl-mfc-shared/reference/csimplestringt-class.md). Erweiterte Funktionen, z. B. Zeichen Manipulation, Sortierung und Suche werden von implementiert `CStringT`.  
  
> [!NOTE]
> `CStringT` Objekte werden können Ausnahmen ausgelöst. Dies tritt auf, wenn ein `CStringT` -Objekt aus irgendeinem Grund nicht genügend Arbeitsspeicher ausgeführt wird.  
  
 Ein `CStringT` Objekt besteht aus einer Zeichenfolge variabler Länge. `CStringT` enthält Funktionen und Operatoren, die der Basic-ähnliche Syntax verwenden. Verkettung und Vergleichsoperatoren, zusammen mit vereinfachten Speicherverwaltungsfunktionen, stellen `CStringT` Objekte, die einfacher zu verwenden als normales Zeichen-Arrays.  
  
> [!NOTE]
>  Obwohl es möglich ist, erstellen Sie `CStringT` Instanzen, die enthalten eingebettete Null-Zeichen, es wird davon abgeraten, es. Aufrufen von Methoden und Operatoren für `CStringT` Objekte, die eingebettete Null-Zeichen enthalten können zu unbeabsichtigte Ergebnissen führen.  
  
 Mit verschiedenen Kombinationen der `BaseType` und `StringTraits` Parameter `CStringT` Objekte kann geht in den folgenden Typen, die sind vordefiniert wurden, durch die ATL-Bibliotheken.  
  
 Wenn in eine ATL-Anwendung verwenden zu können:  
  
 `CString`, `CStringA`, und `CStringW` exportiert werden, über die MFC-DLL (MFC90. (DLL), nie vom Benutzer DLLs. Dies geschieht, um zu verhindern, dass `CStringT` aus mehrfach definiert wird.  
  
> [!NOTE]
>  Wenn der Code die problemumgehung für Linkerfehler, die enthält in beschriebenen [Linking Errors When You Import CString-Derived Klassen "(Q309801)](https://support.microsoft.com/help/309801/you-may-receive-an-lnk2019-error-message-when-you-build-a-visual-c-200), sollten Sie diesen Code entfernen. Es ist nicht mehr benötigt.  
  
 Die folgenden Zeichenfolgen-Datentypen sind in MFC-basierten Anwendungen zur Verfügung:  
  
|CStringT-Typ|Deklaration|  
|-------------------|-----------------|  
|`CStringA`|ANSI-Zeichen geben die Zeichenfolge mit der CRT-Unterstützung.|  
|`CStringW`|Ein Unicode-Zeichen geben die Zeichenfolge mit der CRT-Unterstützung.|  
|`CString`|ANSI- und Unicode-Zeichentypen mit CRT-Unterstützung.|  
  
 Die folgende Zeichenfolge Typen im stehen Projekte, in denen **ATL_CSTRING_NO_CRT** definiert ist:  
  
|CStringT-Typ|Deklaration|  
|-------------------|-----------------|  
|**CAtlStringA**|ANSI-Zeichen Typzeichenfolge ohne CRT-Unterstützung.|  
|**CAtlStringW**|Ein Unicode-Zeichen Typzeichenfolge ohne CRT-Unterstützung.|  
|**CAtlString**|ANSI- und Unicode-Zeichentypen ohne CRT-Unterstützung.|  
  
 Die folgende Zeichenfolge Typen im stehen Projekte, in denen **ATL_CSTRING_NO_CRT** ist nicht definiert:  
  
|CStringT-Typ|Deklaration|  
|-------------------|-----------------|  
|**CAtlStringA**|ANSI-Zeichen geben die Zeichenfolge mit der CRT-Unterstützung.|  
|**CAtlStringW**|Ein Unicode-Zeichen geben die Zeichenfolge mit der CRT-Unterstützung.|  
|**CAtlString**|ANSI- und Unicode-Zeichentypen mit CRT-Unterstützung.|  
  
 `CString` Objekte verfügen außerdem über die folgenden Eigenschaften:  
  
- `CStringT` Objekte können als Ergebnis der Verkettungsvorgänge erweitert werden.  
  
- `CStringT` Führen Sie die Objekte "Wertsemantik". Denken Sie an einer `CStringT` Objekt als eine tatsächliche Zeichenfolge und nicht als ein Zeiger auf eine Zeichenfolge.  
  
-   Sie können beliebig ersetzen `CStringT` von Objekten für die `PCXSTR` Funktionsargumente.  
  
-   Benutzerdefinierte Speicherverwaltung für Zeichenfolgenpuffer. Weitere Informationen finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="cstringt-predefined-types"></a>CStringT vordefinierte Typen  
 Da `CStringT` verwendet ein Vorlagenargument den Zeichentyp definieren (entweder [Wchar_t](../../c-runtime-library/standard-types.md) oder [Char](../../c-runtime-library/standard-types.md)) unterstützt, Parametertypen der Methode kann kompliziert vorkommen. Um dieses Problem zu vereinfachen, eine Reihe von vordefinierten Typen definiert und verwendet die `CStringT` Klasse. In der folgenden Tabelle sind die verschiedenen Typen aufgeführt:  
  
|name|Beschreibung|  
|----------|-----------------|  
|`XCHAR`|Ein einzelnes Zeichen (entweder `wchar_t` oder `char`) mit dem gleichen Zeichen als die `CStringT` Objekt.|  
|**YCHAR**|Ein einzelnes Zeichen (entweder `wchar_t` oder `char`) mit den entgegengesetzten Zeichentyp als die `CStringT` Objekt.|  
|`PXSTR`|Ein Zeiger auf eine Zeichenfolge (entweder `wchar_t` oder `char`) mit dem gleichen Zeichen als die `CStringT` Objekt.|  
|**PYSTR**|Ein Zeiger auf eine Zeichenfolge (entweder `wchar_t` oder `char`) mit den entgegengesetzten Zeichentyp als die `CStringT` Objekt.|  
|`PCXSTR`|Ein Zeiger auf eine **const** Zeichenfolge (entweder `wchar_t` oder `char`) mit dem gleichen Zeichen als die `CStringT` Objekt.|  
|**PCYSTR**|Ein Zeiger auf eine **const** Zeichenfolge (entweder `wchar_t` oder `char`) mit den entgegengesetzten Zeichentyp als die `CStringT` Objekt.|  
  
> [!NOTE]
>  Code, der zuvor nicht dokumentierte Methoden verwendet `CString` (z. B. **AssignCopy**) ersetzt werden muss, mit Code, die folgenden dokumentierten Methoden der verwendet `CStringT` (z. B. `GetBuffer` oder `ReleaseBuffer`). Diese Methoden werden von geerbt `CSimpleStringT`.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)  
  
 `CStringT`  
  
## <a name="requirements"></a>Anforderungen  
  
|Header|Verwenden Sie für|  
|------------|-------------|  
|CStringT.h|Nur MFC Zeichenfolgenobjekten|  
|atlstr.h|MFC-fremde Zeichenfolgenobjekten|  
  
##  <a name="allocsysstring"></a>  CStringT::AllocSysString  
 Ordnet eine Automation-kompatible Zeichenfolge des Typs `BSTR` und kopiert den Inhalt der `CStringT` Objekt hinein, einschließlich des abschließenden Null-Zeichens.  
  
```  
BSTR AllocSysString() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die neu zugeordneten Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 In MFC-Programmen eine [CMemoryException Klasse](../../mfc/reference/cmemoryexception-class.md) wird ausgelöst, wenn nicht genügend Arbeitsspeicher vorhanden ist. ATL-Programme eine [CAtlException](../../atl/reference/catlexception-class.md) ausgelöst wird. Diese Funktion wird normalerweise verwendet, um die Zeichenfolgen für die Automatisierung zurückzugeben.  
  

 Häufig, wenn diese Zeichenfolge an eine COM-Funktion übergeben wird als [in]-Parameter, und dies muss der Aufrufer die Zeichenfolge frei. Dies kann geschehen, indem Sie mithilfe von [SysFreeString](https://msdn.microsoft.com/library/windows/desktop/ms221481.aspx)gemäß der Beschreibung im Windows SDK. Weitere Informationen finden Sie unter [Allocating und Freigeben von Arbeitsspeicher für einen BSTR](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md).  
  
 Weitere Informationen zu OLE-Zuordnungsfunktionen in Windows finden Sie unter [SysAllocString](https://msdn.microsoft.com/library/windows/desktop/ms221458.aspx) im Windows SDK.  

  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CStringT::AllocSysString`.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#105](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]  
  
##  <a name="ansitooem"></a>  CStringT::AnsiToOem  
 Konvertiert alle Zeichen in dieser `CStringT` Objekt aus dem ANSI-Zeichensatz in den OEM-Zeichensatz.  
  
```  
void AnsiToOem();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion ist nicht verfügbar wenn `_UNICODE` definiert ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#106](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]  
  
##  <a name="appendformat"></a>  CStringT::AppendFormat  
 Fügt der formatierte Daten einer vorhandenen `CStringT` Objekt.  
  
```  
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```  
  
### <a name="parameters"></a>Parameter  
 `pszFormat`  
 Eine formatsteuerzeichenfolge.  
  
 `nFormatID`  
 Der Ressourcenbezeichner des Zeichenfolge, die die formatsteuerzeichenfolge enthält.  
  
 `argument`  
 Optionale Argumente.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion formatiert und fügt eine Reihe von Zeichen und Werte in der `CStringT`. Jedes optionales Argument (sofern vorhanden) konvertiert und entsprechend der jeweiligen Formatangabe in angefügt `pszFormat` oder über eine Zeichenfolgenressource identifizierten `nFormatID`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#107](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]  
  
##  <a name="collate"></a>  CStringT::Collate  
 Vergleicht zwei Zeichenfolgen, die mit der Funktion für generischen Text `_tcscoll`.  
  
```  
int Collate(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `psz`  
 Die andere Zeichenfolge für den Vergleich verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 NULL, wenn die Zeichenfolgen identisch sind, < 0, wenn diese `CStringT` Objekt ist kleiner als `psz`, oder > 0, wenn diese `CStringT` -Quellobjekt ist größer als `psz`.  
  
### <a name="remarks"></a>Hinweise  
 Die generische Textfunktion `_tcscoll`, die in TCHAR definiert ist. H, ordnet entweder `strcoll`, `wcscoll`, oder `_mbscoll`, abhängig von den Zeichensatz an, die zum Zeitpunkt der Kompilierung definiert ist. Jede Funktion führt einen Vergleich Groß-/Kleinschreibung der Zeichenfolgen gemäß der Codepage derzeit verwenden. Weitere Informationen finden Sie unter [Strcoll Wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).  
  
##  <a name="collatenocase"></a>  CStringT::CollateNoCase  
 Vergleicht zwei Zeichenfolgen, die mit der Funktion für generischen Text `_tcscoll`.  
  
```  
int CollateNoCase(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `psz`  
 Die andere Zeichenfolge für den Vergleich verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 NULL, wenn die Zeichenfolgen sind identisch (Groß-/Kleinschreibung), < 0, wenn diese `CStringT` Objekt ist kleiner als `psz` (Ignorieren der Groß-/Kleinschreibung), oder > 0, wenn diese `CStringT` -Quellobjekt ist größer als `psz` (Ignorieren der Groß-/Kleinschreibung).  
  
### <a name="remarks"></a>Hinweise  
 Die generische Textfunktion `_tcscoll`, die in TCHAR definiert ist. H, ordnet entweder `stricoll`, `wcsicoll`, oder `_mbsicoll`, abhängig von den Zeichensatz an, die zum Zeitpunkt der Kompilierung definiert ist. Jede Funktion führt einen Vergleich Groß-/Kleinschreibung der Zeichenfolgen, entsprechend der derzeit verwendeten Codepage. Weitere Informationen finden Sie unter [Strcoll Wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#109](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]  
  
##  <a name="compare"></a>  CStringT::Compare  
 Vergleicht zwei Zeichenfolgen (Groß-/Kleinschreibung wird beachtet).  
  
```  
int Compare(PCXSTR psz) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `psz`  
 Die andere Zeichenfolge für den Vergleich verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 NULL, wenn die Zeichenfolgen identisch sind, < 0, wenn diese `CStringT` Objekt ist kleiner als `psz`, oder > 0, wenn diese `CStringT` -Quellobjekt ist größer als `psz`.  
  
### <a name="remarks"></a>Hinweise  
 Die generische Textfunktion `_tcscmp`, die in TCHAR definiert ist. H, ordnet entweder `strcmp`, `wcscmp`, oder `_mbscmp`, abhängig von den Zeichensatz an, die zum Zeitpunkt der Kompilierung definiert ist. Jede Funktion führt einen Vergleich Groß-/Kleinschreibung der Zeichenfolgen und wird nicht vom Gebietsschema beeinflusst. Weitere Informationen finden Sie unter [Strcmp, Wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md).  
  
 Wenn die Zeichenfolge eingebettete NULL-Werte enthält, wird für Vergleichszwecke die Zeichenfolge als bei der ersten eingebettete Null-Zeichen abgeschnitten.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CStringT::Compare`.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#110](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]  
  
##  <a name="comparenocase"></a>  CStringT::CompareNoCase  
 Vergleicht zwei Zeichenfolgen (Groß-/Kleinschreibung beachten).  
  
```  
int CompareNoCase(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `psz`  
 Die andere Zeichenfolge für den Vergleich verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 NULL, wenn die Zeichenfolgen identisch sind (Ignorieren der Groß-/Kleinschreibung), < 0, wenn diese `CStringT` Objekt ist kleiner als `psz` (Ignorieren der Groß-/Kleinschreibung), oder > 0, wenn diese `CStringT` -Quellobjekt ist größer als `psz` (Ignorieren der Groß-/Kleinschreibung).  
  
### <a name="remarks"></a>Hinweise  
 Die generische Textfunktion `_tcsicmp`, die in TCHAR definiert ist. H, ordnet entweder `_stricmp`, `_wcsicmp` oder `_mbsicmp`, abhängig von den Zeichensatz an, die zum Zeitpunkt der Kompilierung definiert ist. Jede Funktion vergleicht Groß-/Kleinschreibung der Zeichenfolgen. Der Vergleich richtet sich nach der `LC_CTYPE` Aspekt des Gebietsschemas, aber nicht `LC_COLLATE`. Weitere Informationen finden Sie unter [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#111](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]  
  
##  <a name="cstringt"></a>  CStringT::CStringT  
 Erstellt ein `CStringT`-Objekt.  
  
```  
CStringT() throw() :   
    CThisSimpleString(StringTraits::GetDefaultManager());
 
explicit CStringT(IAtlStringMgr* pStringMgr) throw() :   
    CThisSimpleString( pStringMgr); 

CStringT(const VARIANT& varSrc);
 
CStringT(const VARIANT& varSrc, IAtlStringMgr* pStringMgr);
 
CStringT(const CStringT& strSrc) :   
    CThisSimpleString( strSrc);

 operator CSimpleStringT<
                    BaseType, 
                    !_CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>
                    :: c_bIsMFCDLLTraits> &()  
 
template <bool bMFCDLL>  
CStringT(const CSimpleStringT<BaseType, bMFCDLL>& strSrc) :   
    CThisSimpleString( strSrc);
 
template <class SystemString>  
CStringT(SystemString^ pString) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const XCHAR* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(const YCHAR* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(LPCSTR pszSrc, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
 
CStringT(LPCWSTR pszSrc, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
 
CSTRING_EXPLICIT CStringT(const unsigned char* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
/*CSTRING_EXPLICIT*/ CStringT(char* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(unsigned char* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(wchar_t* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const unsigned char* pszSrc, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
 
CSTRING_EXPLICIT CStringT(char ch, int nLength = 1) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(wchar_t ch, int nLength = 1) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const XCHAR* pch, int nLength) :   
    CThisSimpleString( pch, nLength, StringTraits::GetDefaultManager());
 
CStringT(const YCHAR* pch, int nLength) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const XCHAR* pch, int nLength, AtlStringMgr* pStringMgr) :   
    CThisSimpleString( pch, nLength, pStringMgr);
 
CStringT(const YCHAR* pch, int nLength, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
```  
  
### <a name="parameters"></a>Parameter  
 `pch`  
 Ein Zeiger auf ein Array von Zeichen Länge `nLength`, nicht auf Null endende.  
  
 `nLength`  
 Die Anzahl der Zeichen im `pch`.  
  
 `ch`  
 Ein einzelnes Zeichen.  
  
 `pszSrc`  
 Eine auf Null endende Zeichenfolge, die in diese kopiert werden `CStringT` Objekt.  
  
 `pStringMgr`  
 Ein Zeiger auf Speicher-Manager für die `CStringT` Objekt. Weitere Informationen zu `IAtlStringMgr` und Verwaltung des Arbeitsspeichers für `CStringT`, finden Sie unter [Speicherverwaltung mit CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
 `strSrc`  
 Eine vorhandene `CStringT` Objekt in diese kopiert werden `CStringT` Objekt. Weitere Informationen zu `CThisString` und `CThisSimpleString`, finden Sie im Abschnitt "Hinweise".  
  
 `varSrc`  
 Ein variant-Objekt in diese kopiert werden `CStringT` Objekt.  
  
 `BaseType`  
 Der Typ der Zeichenfolgenklasse. Einer der folgenden Werte ist möglich:  
  
 `char` (für ANSI-Zeichenfolgen).  
  
 `wchar_t` (für Unicode-Zeichenfolgen).  
  
 `TCHAR` (für ANSI- und Unicode-Zeichenfolgen).  
  
 `bMFCDLL`  
 Boolescher Wert, der angibt, ob das Projekt eine MFC-DLL (TRUE) oder nicht ist (FALSE).  
  
 `SystemString`  
 Muss `System::String`, und das Projekt muss mit "/ CLR" kompiliert werden.  
  
 `pString`  
 Ein Handle für ein `CStringT` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Da die Konstruktoren die Eingabedaten in den neuen belegten Speicher kopieren, sollten Sie bedenken, dass der Arbeitsspeicher Ausnahmen führen können. Beachten Sie, dass einige dieser Konstruktoren als Konvertierungsfunktionen fungieren. Dies bietet die Möglichkeit zu ersetzen, z. B. ein `LPTSTR` , in dem ein `CStringT` Objekt wird erwartet.  
  
- `CStringT`( `LPCSTR` `lpsz` ): Erstellt einen Unicode `CStringT` aus einer ANSI-Zeichenfolge. Sie können diesen Konstruktor auch verwenden, beim Laden einer Zeichenfolgenressource wie im folgenden Beispiel gezeigt.  
  
- `CStringT(` `LPCWSTR` `lpsz` ): Erstellt eine `CStringT` eine Unicode-Zeichenfolge.  
  
- `CStringT`( `const unsigned char*` `psz` ): Ermöglicht es Ihnen so erstellen Sie eine `CStringT` von einem Zeiger auf `unsigned char`.  
  
> [!NOTE]
>  Definieren der **_CSTRING_DISABLE_NARROW_WIDE_CONVERSION** -Makro deaktivieren implizite zeichenfolgenkonvertierung zwischen [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] und [!INCLUDE[TLA#tla_unicode](../../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] Zeichenfolgen. Das Makro schließt aus Kompilierung-Konstruktoren, die Konvertierung zu unterstützen.  
  
 Beachten Sie, dass die `strSrc` Parameter kann es sich um eine `CStringT` oder `CThisSimpleString` Objekt. Für `CStringT`, verwenden Sie den Standard-Instanziierungen ( `CString`, `CStringA`, oder `CStringW`); für `CThisSimpleString`, verwenden Sie eine `this` Zeiger. `CThisSimpleString` deklariert eine Instanz der [CSimpleStringT Klasse](../../atl-mfc-shared/reference/csimplestringt-class.md), also eine kleinere Zeichenfolgenklasse mit weniger integrierter Funktionen als die `CStringT` Klasse.  
  
 Der Überladungsoperator `CSimpleStringT<>&()` erstellt eine `CStringT` -Objekt aus einer `CSimpleStringT` Deklaration.  
  
> [!NOTE]
>  Obwohl es möglich ist, erstellen Sie `CStringT` Instanzen, die enthalten eingebettete Null-Zeichen, es wird davon abgeraten, es. Aufrufen von Methoden und Operatoren für `CStringT` Objekte, die eingebettete Null-Zeichen enthalten können zu unbeabsichtigte Ergebnissen führen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#112](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]  
  
##  <a name="_dtorcstringt"></a>  CStringT:: ~ CStringT  
 Zerstört das `CStringT`-Objekt.  
  
```  
~CStringT() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Zerstört das `CStringT`-Objekt.  
  
##  <a name="delete"></a>  CStringT::Delete  
 Löscht ein Zeichen oder Zeichen aus einer Zeichenfolge, die das Zeichen am angegebenen Index ab.  
  
```  
int Delete(int iIndex, int nCount = 1);
```  
  
### <a name="parameters"></a>Parameter  
 `iIndex`  
 Der nullbasierte Index des ersten Zeichens in die `CStringT` zu löschende Objekt.  
  
 `nCount`  
 Die Anzahl der zu entfernenden Zeichen enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der Zeichenfolge geändert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `nCount` ist länger als die Zeichenfolge, die den Rest der Zeichenfolge entfernt werden sollen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#113](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_8.cpp)]  
  
```Output  
Before: Soccer is best,
    but hockey is quicker!  
After: Soccer best,
    but hockey is quicker!  
```  
  
##  <a name="find"></a>  CStringT::Find  
 Sucht die erste Übereinstimmung eines Zeichens oder einer Teilzeichenfolge dieser Zeichenfolge hinzu.  
  
```  
int Find(PCXSTR pszSub, int iStart=0) const throw();
int Find(XCHAR ch, int iStart=0) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszSub`  
 Eine zu suchende Teilzeichenfolge.  
  
 `iStart`  
 Der Index des Zeichens in die Zeichenfolge, die mit der Suche zu starten, oder 0, um von vorn beginnen.  
  
 `ch`  
 Ein einzelnes Zeichen gesucht werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des ersten Zeichens in dieser `CStringT` -Objekt, das die angeforderte Unterzeichenfolge oder Zeichen entspricht; -1, wenn das Zeichen oder die Teilzeichenfolge nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion ist überladen, sodass sowohl einzelnen Zeichen akzeptieren (ähnlich wie die Funktion zur Laufzeit `strchr`) und Zeichenfolgen (ähnlich wie `strstr`).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#114](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]  
  
##  <a name="findoneof"></a>  CStringT::FindOneOf  
 Diese Zeichenfolge für das erste Zeichen, die jedes Zeichen, die in enthaltenen entspricht sucht `pszCharSet`.  
  
```  
int FindOneOf(PCXSTR pszCharSet) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszCharSet`  
 Die Zeichenfolge, die Zeichen für den Abgleich enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des ersten Zeichens in dieser Zeichenfolge trennt, die auch in `pszCharSet`; 1, wenn keine Übereinstimmung vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Sucht das erste Vorkommen der Zeichen im `pszCharSet`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#115](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]  
  
##  <a name="format"></a>  CStringT::Format  
 Schreibt formatierte Daten in eine `CStringT` in derselben Weise wie [Sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) Datenformate in einem C-Stil-Zeichenarray.  
  
```  
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```  
  
### <a name="parameters"></a>Parameter  
 `nFormatID`  
 Der Ressourcenbezeichner des Zeichenfolge, die die formatsteuerzeichenfolge enthält.  
  
 `pszFormat`  
 Eine formatsteuerzeichenfolge.  
  
 `argument`  
 Optionale Argumente.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion formatiert und speichert eine Folge von Zeichen und Werte in der `CStringT`. Jedes optionales Argument (sofern vorhanden) konvertiert und ausgegeben wird, entsprechend der jeweiligen Formatangabe in `pszFormat` oder über eine Zeichenfolgenressource identifizierten `nFormatID`.  
  
 Der Aufruf schlägt fehl, wenn das String-Objekt selbst als Parameter an angeboten wird `Format`. Beispielsweise verursacht der folgende Code zu unvorhersehbaren Ergebnissen führt:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#116](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]  
  
 Weitere Informationen finden Sie unter [Format Specification Syntax: printf and wprintf Functions (Syntax der Formatangabe: printf- und wprintf-Funktionen)](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#117](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]  
  
##  <a name="formatmessage"></a>  CStringT::FormatMessage  
 Formatiert eine Meldungszeichenfolge.  
  
```  
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```  
  
### <a name="parameters"></a>Parameter  
 `nFormatID`  
 Der Ressourcenbezeichner des Zeichenfolge, die den unformatierten Nachrichtentext enthält.  
  
 `pszFormat`  
 Verweist auf die formatsteuerzeichenfolge. Es fügt überprüft und entsprechend formatiert. Die Formatzeichenfolge ähnelt Laufzeitfunktion `printf`-Formatzeichenfolgen formatieren, außer für die Parameter in beliebiger Reihenfolge eingefügt werden können.  
  
 `argument`  
 Optionale Argumente.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion erfordert als Eingabe eine Nachrichtendefinition. Der Nachrichtendefinition richtet sich nach `pszFormat` oder über eine Zeichenfolgenressource identifizierten `nFormatID`. Kopiert die Funktion Text der Nachricht im Format der `CStringT` einfügen Objekts, verarbeiten eine eingebettete Sequenzen aus, wenn angefordert.  
  
> [!NOTE]
> `FormatMessage` versucht, den Systemspeicher für die neu formatierten Zeichenfolge zuzuordnen. Wenn dieser Versuch fehlschlägt, wird automatisch eine Arbeitsspeicher-Ausnahme ausgelöst.  
  
 Jeder Einfügung benötigen einen entsprechenden Parameter folgt die `pszFormat` oder `nFormatID` Parameter. In den Meldungstext werden verschiedene Escape-Sequenzen unterstützt dynamisch Formatieren der Meldung. Weitere Informationen finden Sie unter Windows [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) Funktion im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#118](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]  
  
##  <a name="formatmessagev"></a>  CStringT::FormatMessageV  
 Formatiert eine Meldungszeichenfolge, die mit einer Liste variabler Argumente an.  
  
```  
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```  
  
### <a name="parameters"></a>Parameter  
 `pszFormat`  
 Verweist auf die formatsteuerzeichenfolge. Es fügt überprüft und entsprechend formatiert. Die Formatzeichenfolge ähnelt Laufzeitfunktion `printf`-Formatzeichenfolgen formatieren, außer für die Parameter in beliebiger Reihenfolge eingefügt werden können.  
  
 `pArgList`  
 Ein Zeiger auf eine Liste von Argumenten.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion erfordert eine Nachrichtendefinition als Eingabe verwendet, gemäß `pszFormat`. Die Funktion übernimmt die formatierten Text und eine Variable Argumentliste auf die `CStringT` -Objekt, verarbeiten eine eingebettete Sequenzen einfügen, wenn angefordert.  
  
> [!NOTE]
> `FormatMessageV` Aufrufe [CStringT::FormatMessage](#formatmessage), die versucht, den Systemspeicher für die neu formatierten Zeichenfolge zuzuordnen. Wenn dieser Versuch fehlschlägt, wird automatisch eine Arbeitsspeicher-Ausnahme ausgelöst.  
  
 Weitere Informationen finden Sie unter Windows [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) Funktion im Windows SDK.  
  
##  <a name="formatv"></a>  CStringT::FormatV  
 Formatiert eine Meldungszeichenfolge, die mit einer Liste variabler Argumente an.  
  
```  
void FormatV(PCXSTR pszFormat, va_list args);
```  
  
### <a name="parameters"></a>Parameter  
 `pszFormat`  
 Verweist auf die formatsteuerzeichenfolge. Es fügt überprüft und entsprechend formatiert. Die Formatzeichenfolge ähnelt Laufzeitfunktion `printf`-Formatzeichenfolgen formatieren, außer für die Parameter in beliebiger Reihenfolge eingefügt werden können.  
  
 `args`  
 Ein Zeiger auf eine Liste von Argumenten.  
  
### <a name="remarks"></a>Hinweise  
 Schreibt eine formatierte Zeichenfolge und eine Variable Argumentliste auf eine `CStringT` Zeichenfolge in der gleichen Weise wie `vsprintf_s` Datenformate in einem C-Stil-Zeichenarray.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#119](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities#120](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]  
  
##  <a name="getenvironmentvariable"></a>  CStringT::GetEnvironmentVariable  
 Legt die Zeichenfolge auf den Wert der angegebenen Umgebungsvariablen.  
  
```  
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```  
  
### <a name="parameters"></a>Parameter  
 `pszVar`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die der Umgebungsvariablen angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Ruft den Wert der angegebenen Variablen aus der Umgebungsblock des aufrufenden Prozesses ab. Der Wert ist in Form einer Null-terminierte Zeichenfolge von Zeichen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#121](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]  
  
##  <a name="insert"></a>  CStringT::Insert  
 Fügt ein einzelnes Zeichen oder eine Teilzeichenfolge am angegebenen Index in der Zeichenfolge ein.  
  
```  
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```  
  
### <a name="parameters"></a>Parameter  
 `iIndex`  
 Der Index des Zeichens vor dem Einfügen stattfinden soll.  
  
 `psz`  
 Ein Zeiger auf die Teilzeichenfolge eingefügt werden.  
  
 `ch`  
 Das Zeichen, das eingefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der Zeichenfolge geändert.  
  
### <a name="remarks"></a>Hinweise  
 Die `iIndex` Parameter identifiziert das erste Zeichen, das verschoben wird, um Platz für das Zeichen oder eine Teilzeichenfolge bereitzustellen. Wenn `nIndex` ist 0 (null), die Einfügemarke wird vor die gesamte Zeichenfolge auftreten. Wenn `nIndex` ist größer als die Länge der Zeichenfolge, die Funktion die vorhandene Zeichenfolge verketten wird und das neue Material bereitgestellt wird, entweder durch `ch` oder `psz`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#122](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]  
  
##  <a name="left"></a>  CStringT::Left  
 Extrahiert die `nCount` äußersten linken Zeichen aus diesem `CStringT`-Objekt und gibt eine Kopie der extrahierten Teilzeichenfolge zurück.  
  
```  
CStringT Left(int nCount) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `nCount`  
 Die Anzahl der aus diesem `CStringT`-Objekt zu extrahierenden Zeichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CStringT`-Objekt, das eine Kopie des angegebenen Zeichenbereichs enthält. Das zurückgegebene `CStringT`-Objekt ist ggf. leer.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `nCount` die Zeichenfolgenlänge überschreitet, wird die gesamte Zeichenfolge extrahiert. `Left` ähnelt der `Left`-Funktion von ///Visual Basic.  
  
 In Multibytezeichensätzen (MBCS) behandelt `nCount` jede 8-Bit-Sequenz als ein Zeichen, sodass `nCount` die doppelte Anzahl der Multibytezeichen zurückgibt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#123](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]  
  
##  <a name="loadstring"></a>  CStringT::LoadString  
 Liest eine Zeichenfolgenressource Windows, identifizierte `nID`, in einem vorhandenen `CStringT` Objekt.  
  
```  
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `hInstance`  
 Ein Handle für die Instanz des Moduls.  
  
 `nID`  
 Ein Windows-Zeichenfolge-Ressourcen-ID.  
  
 `wLanguageID`  
 Die Sprache der Zeichenfolgenressource.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Ladevorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Lädt eine Zeichenfolgenressource ( `nID`) aus dem angegebenen Modul ( `hInstance`) mit der angegebenen Sprache ( `wLanguage`).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#124](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]  
  
##  <a name="makelower"></a>  CStringT::MakeLower  
 Konvertiert die `CStringT` Objekt, das eine Zeichenfolge in Kleinbuchstaben.  
  
```  
CStringT& MakeLower();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die resultierende Zeichenfolge aus Kleinbuchstaben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#125](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]  
  
##  <a name="makereverse"></a>  CStringT::MakeReverse  
 Kehrt die Reihenfolge der Zeichen in der `CStringT` Objekt.  
  
```  
CStringT& MakeReverse();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das resultierende umgekehrt Zeichenfolge.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#126](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]  
  
##  <a name="makeupper"></a>  CStringT::MakeUpper  
 Konvertiert die `CStringT` Objekt, das eine Zeichenfolge in Großbuchstaben.  
  
```  
CStringT& MakeUpper();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die resultierende Zeichenfolge in Großbuchstaben.  
  
### <a name="remarks"></a>Hinweise  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#127](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]  
  
##  <a name="mid"></a>  CStringT::Mid  
 Extrahiert eine Teilzeichenfolge der Länge `nCount` Zeichen aus diesem `CStringT` -Objekt, beginnend an der Position `iFirst` (nullbasiert).  
  
```  
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `iFirst`  
 Der nullbasierte Index des ersten Zeichens in dieser `CStringT` -Objekt, das in der extrahierten Teilzeichenfolge enthalten sein soll.  
  
 `nCount`  
 Die Anzahl der aus diesem `CStringT`-Objekt zu extrahierenden Zeichen. Wenn dieser Parameter nicht angegeben ist, wird der Rest der Zeichenfolge extrahiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CStringT`-Objekt, das eine Kopie des angegebenen Zeichenbereichs enthält. Beachten Sie, dass das zurückgegebene `CStringT` Objekt kann leer sein.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion gibt eine Kopie der extrahierten Teilzeichenfolge zurück. `Mid` ähnelt der grundlegenden Mid-Funktion (außer, dass Indizes in Basic einsbasierte sind).  
  
 Für Mehrbyte-Zeichensätzen (MBCS), setzt `nCount` bezieht sich auf jede 8-Bit-Zeichen; bedeutet, dass ein führendes und nachfolgendes Byte in einem multibyte-Zeichen als zwei Zeichen gezählt werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#128](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]  
  
##  <a name="oemtoansi"></a>  CStringT::OemToAnsi  
 Konvertiert alle Zeichen in dieser `CStringT` Objekt aus dem OEM-Zeichensatz der ANSI-Zeichensatz.  
  
```  
void OemToAnsi();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist nicht verfügbar wenn `_UNICODE` definiert ist.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CStringT::AnsiToOem](#ansitooem).  
  
##  <a name="operator_add"></a>  CStringT::operator +  
 Verkettet zwei Zeichenfolgen oder ein Zeichen und eine Zeichenfolge.  
  
```  
friend CStringT operator+(const CStringT& str1, const CStringT& str2);
friend CStringT operator+(const CStringT& str1, PCXSTR psz2);
friend CStringT operator+(PCXSTR psz1, const CStringT& str2,);
friend CStringT operator+(char ch1, const CStringT& str2,);
friend CStringT operator+(const CStringT& str1, char ch2);
friend CStringT operator+(const CStringT& str1, wchar_t ch2);
friend CStringT operator+(wchar_t ch1, const CStringT& str2,);
```  
  
### <a name="parameters"></a>Parameter  
 `ch1`  
 Eine ANSI- oder Unicode-Zeichen mit einer Zeichenfolge verketten.  
  
 `ch2`  
 Eine ANSI- oder Unicode-Zeichen mit einer Zeichenfolge verketten.  
  
 `str1`  
 Ein `CStringT` mit einem Zeichen oder einer Zeichenfolge verketten.  
  
 `str2`  
 Ein `CStringT` mit einem Zeichen oder einer Zeichenfolge verketten.  
  
 `psz1`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge mit einem Zeichen oder einer Zeichenfolge verketten.  
  
 `psz2`  
 Ein Zeiger auf eine Zeichenfolge mit einem Zeichen oder einer Zeichenfolge verketten.  
  
### <a name="remarks"></a>Hinweise  
 Es gibt sieben Überladung Formen von der `CStringT::operator+` Funktion. Die erste Version verkettet zwei vorhandene `CStringT` Objekte. Die nächsten beiden Verketten einer `CStringT` Objekt und eine Null-terminierte Zeichenfolge. Die nächsten beiden Verketten einer `CStringT` -Objekt und ein ANSI-Zeichen. Die letzten zwei Verketten einer `CStringT` -Objekt und ein Unicode-Zeichen.  
  
> [!NOTE]
>  Obwohl es möglich ist, erstellen Sie `CStringT` Instanzen, die enthalten eingebettete Null-Zeichen, es wird davon abgeraten, es. Aufrufen von Methoden und Operatoren für `CStringT` Objekte, die eingebettete Null-Zeichen enthalten können zu unbeabsichtigte Ergebnissen führen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#140](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]  
  
##  <a name="operator_add_eq"></a>  CStringT::operator +=  
 Verkettet die Zeichen bis zum Ende der Zeichenfolge.  
  
```  
CStringT& operator+=(const CThisSimpleString& str);

template<bool bMFCDLL>  
CStringT& operator+=(const const CSimpleStringT<BaseType, bMFCDLL>& str);

template<int t_nSize>  
CStringT& operator+=(const CStaticString<XCHAR, t_nSize>& strSrc);
CStringT& operator+=(PCXSTR pszSrc);
CStringT& operator+=(PCYSTR pszSrc);
CStringT& operator+=(char ch);
CStringT& operator+=(unsigned char ch);
CStringT& operator+=(wchar_t ch);
CStringT& operator+=(const VARIANT& var);
```  
  
### <a name="parameters"></a>Parameter  
 str  
 Ein Verweis auf ein `CThisSimpleString`-Objekt.  
  
 `bMFCDLL`  
 Ein boolescher Wert, der angibt, ob das Projekt eine MFC-DLL oder nicht ist.  
  
 `BaseType`  
 Der Basistyp Zeichenfolge.  
  
 `var`  
 Ein variant-Objekt, der mit dieser Zeichenfolge verkettet.  
  
 `ch`  
 Eine ANSI- oder Unicode-Zeichen mit einer Zeichenfolge verketten.  
  
 `pszSrc`  
 Ein Zeiger auf die ursprüngliche Zeichenfolge verkettet wird.  
  
 `strSrc`  
 Ein `CStringT` , der mit dieser Zeichenfolge verkettet.  
  
### <a name="remarks"></a>Hinweise  
 Der Operator akzeptiert eine andere `CStringT` -Objekt, ein Zeichenzeiger oder ein einzelnes Zeichen. Sie sollten sich bewusst sein, dass der Arbeitsspeicher beim dieser Concatenation-Operator verwenden, da Sie neuer Speicher für Zeichen hinzugefügt, die dieser zugewiesen werden kann, können Ausnahmen auftreten `CStringT` Objekt.  
  
 Informationen zu `CThisSimpleString`, finden Sie im Abschnitt "Hinweise" der [CStringT::CStringT](#cstringt).  
  
> [!NOTE]
>  Obwohl es möglich ist, erstellen Sie `CStringT` Instanzen, die enthalten eingebettete Null-Zeichen, es wird davon abgeraten, es. Aufrufen von Methoden und Operatoren für `CStringT` Objekte, die eingebettete Null-Zeichen enthalten können zu unbeabsichtigte Ergebnissen führen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#141](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]  
  
##  <a name="operator_eq_eq"></a>  CStringT::operator ==  
 Bestimmt, ob zwei Zeichenfolgen logisch gleich sind.  
  
```  
friend bool operator==(const CStringT& str1, const CStringT& str2) throw();
friend bool operator==(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator==(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator==(const CStringT& str1, XCHAR ch2) throw();
friend bool operator==(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator==(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator==(XCHAR ch1, const CStringT& str2,) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ch1`  
 Eine ANSI- oder Unicode-Zeichen für den Vergleich.  
  
 `ch2`  
 Eine ANSI- oder Unicode-Zeichen für den Vergleich.  
  
 `str1`  
 Ein `CStringT` für den Vergleich.  
  
 `str2`  
 Ein `CStringT` für den Vergleich.  
  
 `psz1`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.  
  
 `psz2`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.  
  
### <a name="remarks"></a>Hinweise  
 Testet, ob ein Zeichenfolgen- oder auf der linken Seite eine Zeichenfolge oder ein Zeichen auf der rechten Seite gleich ist, und "true" oder "false" entsprechend gibt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#142](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]  
  
##  <a name="operator_neq"></a>  CStringT::operator! =  
 Bestimmt, ob zwei Zeichenfolgen logisch nicht gleich sind.  
  
```  
friend bool operator!=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator!=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator!=(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator!=(const CStringT& str1, XCHAR ch2) throw();
friend bool operator!=(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator!=(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator!=(XCHAR ch1, const CStringT& str2,) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ch1`  
 Eine ANSI- oder Unicode-Zeichen mit einer Zeichenfolge verketten.  
  
 `ch2`  
 Eine ANSI- oder Unicode-Zeichen mit einer Zeichenfolge verketten.  
  
 `str1`  
 Ein `CStringT` für den Vergleich.  
  
 `str2`  
 Ein `CStringT` für den Vergleich.  
  
 `psz1`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.  
  
 `psz2`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.  
  
### <a name="remarks"></a>Hinweise  
 Testet, ob eine Zeichenfolge oder ein Zeichen auf der linken Seite ungleich einen Zeichenfolgen- oder auf der rechten Seite ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#143](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]  
  
##  <a name="operator_lt"></a>  CStringT::operator &lt;  
 Bestimmt, ob die Zeichenfolge auf der linken Seite des Operators kleiner als die Zeichenfolge auf der rechten Seite ist.  
  
```  
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `str1`  
 Ein `CStringT` für den Vergleich.  
  
 `str2`  
 Ein `CStringT` für den Vergleich.  
  
 `psz1`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.  
  
 `psz2`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.  
  
### <a name="remarks"></a>Hinweise  
 Einen lexikografischen Vergleich zwischen den Zeichenfolgen und Zeichen für Zeichen bis:  
  
-   Er zwei korrespondierende ungleiche Zeichen findet, und deren Vergleich als Ergebnis des Vergleichs zweier Zeichenfolgen genommen wird.  
  
-   Er keine Ungleichheiten findet, aber eine Zeichenfolge mehr Zeichen hat als die andere und die kürzere Zeichenfolge als kleiner als die längere Zeichenfolge betrachtet wird.  
  
-   Er keine Ungleichheiten findet und feststellt, dass die Zeichenfolgen die gleiche Anzahl von Zeichen haben und daher gleich sind.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#144](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]  
  
##  <a name="operator_gt"></a>  CStringT::operator &gt;  
 Bestimmt, ob die Zeichenfolge auf der linken Seite des Operators größer als die Zeichenfolge auf der rechten Seite ist.  
  
```  
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `str1`  
 Ein `CStringT` für den Vergleich.  
  
 `str2`  
 Ein `CStringT` für den Vergleich.  
  
 `psz1`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.  
  
 `psz2`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.  
  
### <a name="remarks"></a>Hinweise  
 Einen lexikografischen Vergleich zwischen den Zeichenfolgen und Zeichen für Zeichen bis:  
  
-   Er zwei korrespondierende ungleiche Zeichen findet, und deren Vergleich als Ergebnis des Vergleichs zweier Zeichenfolgen genommen wird.  
  
-   Er keine Ungleichheiten findet, aber eine Zeichenfolge mehr Zeichen hat als die andere und die kürzere Zeichenfolge als kleiner als die längere Zeichenfolge betrachtet wird.  
  
-   Er keine Ungleichheiten findet und feststellt, dass die Zeichenfolgen die gleiche Anzahl von Zeichen haben und daher gleich sind.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#145](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]  
  
##  <a name="operator_lt_eq"></a>  CStringT::operator &lt;=  
 Bestimmt, ob die Zeichenfolge auf der linken Seite des Operators kleiner als oder gleich der Zeichenfolge auf der rechten Seite ist.  
  
```  
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `str1`  
 Ein `CStringT` für den Vergleich.  
  
 `str2`  
 Ein `CStringT` für den Vergleich.  
  
 `psz1`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.  
  
 `psz2`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.  
  
### <a name="remarks"></a>Hinweise  
 Einen lexikografischen Vergleich zwischen den Zeichenfolgen und Zeichen für Zeichen bis:  
  
-   Er zwei korrespondierende ungleiche Zeichen findet, und deren Vergleich als Ergebnis des Vergleichs zweier Zeichenfolgen genommen wird.  
  
-   Er keine Ungleichheiten findet, aber eine Zeichenfolge mehr Zeichen hat als die andere und die kürzere Zeichenfolge als kleiner als die längere Zeichenfolge betrachtet wird.  
  
-   Er keine Ungleichheiten findet und feststellt, dass die Zeichenfolgen die gleiche Anzahl von Zeichen haben und daher gleich sind.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#146](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]  
  
##  <a name="operator_gt_eq"></a>  CStringT::operator &gt;=  
 Bestimmt, ob die Zeichenfolge auf der linken Seite des Operators größer als oder gleich der Zeichenfolge auf der rechten Seite ist.  
  
```  
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `str1`  
 Ein `CStringT` für den Vergleich.  
  
 `str2`  
 Ein `CStringT` für den Vergleich.  
  
 `psz1`  
 Ein Zeiger auf eine Zeichenfolge für den Vergleich.  
  
 `psz2`  
 Ein Zeiger auf eine Zeichenfolge für den Vergleich.  
  
### <a name="remarks"></a>Hinweise  
 Einen lexikografischen Vergleich zwischen den Zeichenfolgen und Zeichen für Zeichen bis:  
  
-   Er zwei korrespondierende ungleiche Zeichen findet, und deren Vergleich als Ergebnis des Vergleichs zweier Zeichenfolgen genommen wird.  
  
-   Er keine Ungleichheiten findet, aber eine Zeichenfolge mehr Zeichen hat als die andere und die kürzere Zeichenfolge als kleiner als die längere Zeichenfolge betrachtet wird.  
  
-   Er keine Ungleichheiten findet und feststellt, dass die Zeichenfolgen die gleiche Anzahl von Zeichen haben und daher gleich sind.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#147](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]  
  
##  <a name="remove"></a>  CStringT::Remove  
 Entfernt alle Instanzen des angegebenen Zeichens in der Zeichenfolge an.  
  
```  
int Remove(XCHAR chRemove);
```  
  
### <a name="parameters"></a>Parameter  
 `chRemove`  
 Das Zeichen aus einer Zeichenfolge entfernt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeichen aus der Zeichenfolge entfernt. 0 (null), wenn die Zeichenfolge nicht geändert wird.  
  
### <a name="remarks"></a>Hinweise  
 Vergleiche für das Zeichen werden Groß-/Kleinschreibung beachtet.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#129](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]  
  
##  <a name="replace"></a>  CStringT::Replace  
 Es gibt zwei Versionen des `Replace`. Die erste Version ersetzt eine oder mehrere Kopien einer Teilzeichenfolge durch eine andere Teilzeichenfolge. Beide Teilzeichenfolgen sind Null-terminiert. Die zweite Version ersetzt eine oder mehrere Kopien eines Zeichens durch ein anderes Zeichen. Beide Versionen ausgeführt werden, für die Zeichendaten in gespeicherten `CStringT`.  
  
```  
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```  
  
### <a name="parameters"></a>Parameter  
 `pszOld`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge durch ersetzt werden soll `pszNew`.  
  
 `pszNew`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die ersetzt `pszOld`.  
  
 `chOld`  
 Das Zeichen zu ersetzen durch `chNew`.  
  
 `chNew`  
 Ersetzen von Zeichen `chOld`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl von ersetzten Instanzen der Schrägstrich oder Substring oder 0 (null) zurück, wenn die Zeichenfolge nicht geändert wird.  
  
### <a name="remarks"></a>Hinweise  
 `Replace` die Länge der Zeichenfolge kann geändert werden, weil `pszNew` und `pszOld` müssen nicht dieselbe Länge aufweisen und mehrere Kopien der alten Teilzeichenfolge in das neue Projekt geändert werden können. Die Funktion führt eine Übereinstimmung der Groß-/Kleinschreibung beachtet.  
  
 Beispiele für `CStringT` Instanzen sind `CString`, `CStringA`, und `CStringW`.  
  
 Für `CStringA`, `Replace` arbeitet mit ANSI- oder Multibytezeichen (MBCS). Für `CStringW`, `Replace` arbeitet mit Breitzeichen.  
  
 Für `CString`, zum Zeitpunkt der Kompilierung der Zeichendatentyp ausgewählt ist, basierend auf, ob die Konstanten in der folgenden Tabelle definiert werden.  
  
|Definierten Konstanten|Zeichendatentyp|  
|----------------------|-------------------------|  
|`_UNICODE`|Breitzeichen|  
|`_MBCS`|Multi-Byte-Zeichen|  
|Weder|Einzelbyte-Zeichen|  
|Beides|Nicht definiert|  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#200](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]  
  
##  <a name="reversefind"></a>  CStringT::ReverseFind  
 Sucht das `CStringT` Objekt für die letzte Übereinstimmung eines Zeichens.  
  
```  
int ReverseFind(XCHAR ch) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ch`  
 Das zu suchende Zeichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des letzten Zeichens in dieser `CStringT` -Objekt, das das angeforderte Zeichen oder -1 entspricht, sofern diese nicht die Zeichen gefunden wurde.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion ist vergleichbar mit der Funktion zur Laufzeit `strrchr`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#130](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]  
  
##  <a name="right"></a>  CStringT::Right  
 Extrahiert die letzte (d. h. ganz rechts) `nCount` Zeichen aus diesem `CStringT` -Objekt und gibt eine Kopie der extrahierten Teilzeichenfolge zurück.  
  
```  
CStringT Right(int nCount) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `nCount`  
 Die Anzahl der aus diesem `CStringT`-Objekt zu extrahierenden Zeichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CStringT`-Objekt, das eine Kopie des angegebenen Zeichenbereichs enthält. Beachten Sie, dass das zurückgegebene `CStringT` Objekt kann leer sein.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `nCount` die Zeichenfolgenlänge überschreitet, wird die gesamte Zeichenfolge extrahiert. `Right` gleicht die grundlegende `Right` -Funktion (außer, dass Indizes in Basic nullbasiert sind).  
  
 Für Mehrbyte-Zeichensätzen (MBCS), setzt `nCount` bezieht sich auf jede 8-Bit-Zeichen; bedeutet, dass ein führendes und nachfolgendes Byte in einem multibyte-Zeichen als zwei Zeichen gezählt werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#131](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]  
  
##  <a name="setsysstring"></a>  CStringT::SetSysString  
 Zuordnet der `BSTR` verweist `pbstr` und kopiert den Inhalt der `CStringT` Objekt hinein, einschließlich der `NULL` Zeichen.  
  
```  
BSTR SetSysString(BSTR* pbstr) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `pbstr`  
 Ein Zeiger auf eine Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Die neue Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Abhängig vom Inhalt der `CStringT` -Objekt, das der Wert der `BSTR` verwiesen wird, indem Sie `pbstr` ändern können. Löst die Funktion eine `CMemoryException` Wenn nicht genügend Arbeitsspeicher vorhanden ist.  
  
 Diese Funktion wird normalerweise verwendet, um den Wert von Zeichenfolgen, die als Verweis übergeben wird, für die Automatisierung zu ändern.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#132](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]  
  
##  <a name="spanexcluding"></a>  CStringT::SpanExcluding  
 Extrahiert Zeichen aus der Zeichenfolge, beginnend mit dem ersten Zeichen, die nicht in den Satz von Zeichen, die erkennbar sind `pszCharSet`.  
  
```  
CStringT SpanExcluding(PCXSTR pszCharSet) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `pszCharSet`  
 Eine Zeichenfolge, die als einen Satz von Zeichen interpretiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer Teilzeichenfolge, die Zeichen in der Zeichenfolge enthält, die nicht Bestandteil `pszCharSet`, mit dem ersten Zeichen in der Zeichenfolge beginnt und endet mit dem ersten Zeichen in der Zeichenfolge, die auch in gefunden `pszCharSet` (d. h. beginnend mit dem ersten Zeichen in der Zeichenfolge, und bis zum jedoch ohne das erste Zeichen in der Zeichenfolge, die gefunden `pszCharSet`). Wird die gesamte Zeichenfolge zurückgegeben, wenn kein Zeichen in `pszCharSet` befindet sich in der Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 `SpanExcluding` extrahiert und gibt alle Zeichen, die vor das erste Vorkommen eines Zeichens vom `pszCharSet` (das heißt, das Zeichen aus `pszCharSet` und alle Zeichen in der Zeichenfolge folgt nicht zurückgegeben werden). Wenn kein Zeichen aus `pszCharSet` befindet sich in der Zeichenfolge anschließend `SpanExcluding` die gesamte Zeichenfolge zurückgegeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#133](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]  
  
##  <a name="spanincluding"></a>  CStringT::SpanIncluding  
 Extrahiert Zeichen aus der Zeichenfolge, beginnend mit dem ersten Zeichen, die in den Satz von Zeichen, die erkennbar sind `pszCharSet`.  
  
```  
CStringT SpanIncluding(PCXSTR pszCharSet) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `pszCharSet`  
 Eine Zeichenfolge, die als einen Satz von Zeichen interpretiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Teilzeichenfolge, die Zeichen in der Zeichenfolge, die in sind enthält `pszCharSet`, mit dem ersten Zeichen in der Zeichenfolge beginnt und endet, wenn ein Zeichen in der Zeichenfolge gefunden wird, der nicht `pszCharSet`. `SpanIncluding` Gibt eine leere Teilzeichenfolge zurück, wenn das erste Zeichen in der Zeichenfolge nicht in der angegebenen Menge vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Ist das erste Zeichen der Zeichenfolge nicht im Zeichensatz, klicken Sie dann `SpanIncluding` eine leere Zeichenfolge zurückgegeben. Andernfalls wird eine Folge von aufeinander folgenden Zeichen, die in der Menge zurückgegeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#134](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]  
  
##  <a name="tokenize"></a>  CStringT::Tokenize  
 Sucht das nächste Token in eine Zielzeichenfolge  
  
```  
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `pszTokens`  
 Eine Zeichenfolge, die token-Trennzeichen enthält. Die Reihenfolge der diese Trennzeichen ist nicht wichtig.  
  
 `iStart`  
 Der nullbasierte Index, um die Suche zu starten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CStringT` Objekt, das den aktuellen Tokenwert enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die `Tokenize` -Funktion sucht das nächste Token in der Zielzeichenfolge. Der Satz von Zeichen im `pszTokens` gibt mögliche Trennzeichen des Tokens gefunden werden. Bei jedem Aufruf `Tokenize` die Funktion beginnt am `iStart`, überspringt vorangestellte Trennzeichen, und gibt ein `CStringT` Objekt, das das aktuelle Token, also die Zeichenfolge von Zeichen bis zum nächsten Trennzeichen enthält. Der Wert des `iStart` wird aktualisiert, um die Position nach Trennzeichen Endzeichen oder -1, wenn das Ende der Zeichenfolge erreicht wurde. Weitere Token können geholt werden im weiteren Verlauf der Zielzeichenfolge durch eine Reihe von Aufrufen an `Tokenize`mit `iStart` zum Nachverfolgen, an welcher Stelle der Zeichenfolge entspricht, dass das nächste Token gelesen werden. Wenn es keine Token mehr sind gibt die Funktion eine leere Zeichenfolge zurück und `iStart` wird auf-1 festgelegt werden.  
  
 Im Gegensatz zu der CRT mit Token zu versehen Funktionen wie [Strtok_s _strtok_s_l, Wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md), `Tokenize` die Zielzeichenfolge nicht geändert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#135](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]  
  
### <a name="remarks"></a>Hinweise  
 In diesem Beispiel wird die Ausgabe lautet wie folgt:  
  
 `Resulting Token: First`  
  
 `Resulting Token: Second`  
  
 `Resulting Token: Third`  
  
##  <a name="trim"></a>  CStringT::Trim  
 Entfernt führende und nachfolgende Zeichen aus der Zeichenfolge.  
  
```  
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```  
  
### <a name="parameters"></a>Parameter  
 `chTarget`  
 Das Ziel Zeichen gekürzt werden.  
  
 `pszTargets`  
 Ein Zeiger auf eine Zeichenfolge, die das Ziel zu kürzenden Zeichen enthält. Alle führenden und nachgestellten Vorkommen der Zeichen im `pszTarget` abgeschnitten aus der `CStringT` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die zugeschnittene Zeichenfolge zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Entfernt alle führende und nachgestellte Vorkommen eines der folgenden:  
  
-   Durch angegebene Zeichen `chTarget.`  
  
-   Alle Zeichen in der Zeichenfolge durch angegebene gefunden `pszTargets.`  
  
-   Leerzeichen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#136](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]  
  
### <a name="remarks"></a>Hinweise  
 In diesem Beispiel wird die Ausgabe lautet wie folgt:  
  
 `Before: "******Soccer is best, but liquor is quicker!!!!!"`  
  
 `After : "Soccer is best, but liquor is quicker"`  
  
##  <a name="trimleft"></a>  CStringT::TrimLeft  
 Schneidet das führende Zeichen aus der Zeichenfolge.  
  
```  
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```  
  
### <a name="parameters"></a>Parameter  
 `chTarget`  
 Das Ziel Zeichen gekürzt werden.  
  
 `pszTargets`  
 Ein Zeiger auf eine Zeichenfolge, die das Ziel zu kürzenden Zeichen enthält. Alle nachgestellten Vorkommen der Zeichen im `pszTarget` abgeschnitten aus der `CStringT` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die resultierende zugeschnittene Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Entfernt alle führende und nachgestellte Vorkommen eines der folgenden:  
  
-   Durch angegebene Zeichen `chTarget.`  
  
-   Alle Zeichen in der Zeichenfolge durch angegebene gefunden `pszTargets.`  
  
-   Leerzeichen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#137](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]  
  
##  <a name="trimright"></a>  CStringT::TrimRight  
 Schneidet das nachfolgende Zeichen aus der Zeichenfolge.  
  
```  
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```  
  
### <a name="parameters"></a>Parameter  
 `chTarget`  
 Das Ziel Zeichen gekürzt werden.  
  
 `pszTargets`  
 Ein Zeiger auf eine Zeichenfolge, die das Ziel zu kürzenden Zeichen enthält. Alle nachgestellten Vorkommen der Zeichen im `pszTarget` abgeschnitten aus der `CStringT` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die `CStringT` Objekt, das die zugeschnittene Zeichenfolge enthält.  
  
### <a name="remarks"></a>Hinweise  
 Entfernt einen nachgestellten Vorkommen eines der folgenden:  
  
-   Durch angegebene Zeichen `chTarget.`  
  
-   Alle Zeichen in der Zeichenfolge durch angegebene gefunden `pszTargets.`  
  
-   Leerzeichen.  
  
 Die `CStringT& TrimRight(XCHAR chTarget)` Version einen Zeichenparameter annimmt und entfernt alle Kopien dieses Zeichen vom Ende `CStringT` Zeichenfolgendaten. Am Ende der Zeichenfolge beginnt und funktioniert nach vorn. Es beendet, wenn ein anderes Zeichen gefunden wird oder wenn `CSTringT` nicht mehr genügend Zeichendaten.  
  
 Die `CStringT& TrimRight(PCXSTR pszTargets)` Version akzeptiert eine auf Null endende Zeichenfolge, die alle anderen Zeichen zu suchende enthält. Entfernt alle Kopien dieser Zeichen in der `CStringT` Objekt. Er beginnt am Ende der Zeichenfolge und funktioniert nach vorn. Es beendet, wenn ein Zeichen gefunden werden, die nicht in der Zielzeichenfolge enthalten ist, oder wenn `CStringT` nicht mehr genügend Zeichendaten. Es wird kein Verbindungsversuch mit einer Teilzeichenfolge am Ende die gesamten Zielzeichenfolge entsprechend `CStringT`.  
  
 Die `CStringT& TrimRight()` Version erfordert keine Parameter. Um anzupassen, dass keine nachfolgenden Leerzeichen am Ende der `CStringT` Zeichenfolge. Leerzeichen können Zeilenumbrüche, Leerzeichen oder Tabstopps sein.  
  
-  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#138](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)   
 [CSimpleStringT-Klasse](../../atl-mfc-shared/reference/csimplestringt-class.md)


