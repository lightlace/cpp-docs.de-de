---
title: CStringT-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CString
- CStringT
- ATL::CStringT
- ATL.CStringT
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], in ATL
- shared classes, CStringT
- CStringT class
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
caps.latest.revision: 33
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
ms.openlocfilehash: 9660db5ff0d41a31f7d2a4e824df4e4bdf6a00e6
ms.lasthandoff: 02/24/2017

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
 Der Typ der String-Klasse. Einer der folgenden Werte ist möglich:  
  
- `char`(für ANSI-Zeichenfolgen).  
  
- `wchar_t`(für Unicode-Zeichenfolgen).  
  
- **TCHAR** (nach ANSI- und Unicode-Zeichenfolgen).  
  
 `StringTraits`  
 Bestimmt, ob die String-Klasse benötigt Unterstützung für C-Laufzeit (CRT)-Bibliothek und dem Zeichenfolgenressourcen gespeichert werden. Einer der folgenden Werte ist möglich:  
  
- **StrTraitATL<> </> ** | `char` | **TCHAR, ChTraitsCRT<> </> ** | `char` | **TCHAR > >**  
  
     Die Klasse erfordert CRT-Unterstützung und sucht nach Zeichenfolgen im angegebenen Modul `m_hInstResource` (ein Mitglied der Anwendung Module-Klasse).  
  
- **StrTraitATL<> </> ** | `char` | **TCHAR, ChTraitsOS<> </> ** | `char` | **TCHAR > >**  
  
     Die Klasse erfordert keine CRT-Unterstützung und sucht nach Zeichenfolgen im angegebenen Modul `m_hInstResource` (ein Mitglied der Anwendung Module-Klasse).  
  
- **StrTraitMFC<> </> ** | `char` | **TCHAR, ChTraitsCRT<> </> ** | `char` | **TCHAR > >**  
  
     Die Klasse erfordert CRT-Unterstützung und sucht mithilfe der standardmäßigen MFC Suchalgorithmus Ressourcenzeichenfolgen.  
  
- **StrTraitMFC<> </> ** | `char` | **TCHAR, ChTraitsOS<> </> ** | `char` | **TCHAR > >**  
  
     Die Klasse erfordert keine CRT-Unterstützung und sucht mithilfe der standardmäßigen MFC Suchalgorithmus Ressourcenzeichenfolgen.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStringT::CStringT](#cstringt)|Erstellt ein `CStringT` Objekt auf verschiedene Weise.|  
|[CStringT:: ~ CStringT](#_dtorcstringt)|Zerstört ein `CStringT`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStringT::AllocSysString](#allocsysstring)|Ordnet eine `BSTR` von `CStringT` Daten.|  
|[CStringT::AnsiToOem](#ansitooem)|Stellt eine direkte Konvertierung von ANSI-Zeichensatz in den OEM-Zeichensatz.|  
|[CStringT::AppendFormat](#appendformat)|Fügt der formatierte Daten einer vorhandenen `CStringT` Objekt.|  
|[CStringT::Collate](#collate)|Vergleicht zwei Zeichenfolgen (Groß-und Kleinschreibung unterschieden, verwendet gebietsschemaspezifischen Informationen).|  
|[CStringT::CollateNoCase](#collatenocase)|Vergleicht zwei Zeichenfolgen (Groß-/Kleinschreibung, verwendet gebietsschemaspezifischen Informationen).|  
|[CStringT::Compare](#compare)|Vergleicht zwei Zeichenfolgen (Groß-/Kleinschreibung wird beachtet).|  
|[CStringT::CompareNoCase](#comparenocase)|Vergleicht zwei Zeichenfolgen (ohne Berücksichtigung der Groß-und Kleinschreibung).|  
|[CStringT::Delete](#delete)|Löscht ein oder mehrere Zeichen aus einer Zeichenfolge.|  
|[CStringT::Find](#find)|Sucht ein Zeichen oder eine Teilzeichenfolge innerhalb einer größeren Zeichenfolge.|  
|[CStringT::FindOneOf](#findoneof)|Sucht das erste übereinstimmende Zeichen aus einem Satz.|  
|[CStringT::Format](#format)|Formatiert die Zeichenfolge als `sprintf` ist.|  
|[CStringT::FormatMessage](#formatmessage)|Formatiert eine Meldungszeichenfolge.|  
|[CStringT::FormatMessageV](#formatmessagev)|Formatiert eine Zeichenfolge mit einer Liste variabler Argumente.|  
|[CStringT::FormatV](#formatv)|Formatiert die Zeichenfolge, die eine Variable Liste mit Argumenten verwenden.|  
|[CStringT::GetEnvironmentVariable](#getenvironmentvariable)|Die Zeichenfolge wird auf den Wert der angegebenen Umgebungsvariablen festgelegt.|  
|[CStringT::Insert](#insert)|Fügt ein einzelnes Zeichen oder eine Teilzeichenfolge am angegebenen Index in der Zeichenfolge.|  
|[CStringT::Left](#left)|Extrahiert den linken Teil einer Zeichenfolge.|  
|[CStringT::LoadString](#loadstring)|Lädt eine vorhandene `CStringT` Objekt aus einer Windows-Ressource.|  
|[CStringT::MakeLower](#makelower)|Konvertiert alle Zeichen in dieser Zeichenfolge in Kleinbuchstaben.|  
|[CStringT::MakeReverse](#makereverse)|Kehrt die Zeichenfolge an.|  
|[CStringT::MakeUpper](#makeupper)|Konvertiert alle Zeichen in dieser Zeichenfolge in Großbuchstaben.|  
|[CStringT::Mid](#mid)|Extrahiert den mittleren Teil einer Zeichenfolge.|  
|[CStringT::OemToAnsi](#oemtoansi)|Stellt eine direkte Konvertierung vom OEM-Zeichensatz in den ANSI-Zeichensatz.|  
|[CStringT::Remove](#remove)|Entfernt einen angegebenen Zeichen aus einer Zeichenfolge.|  
|[CStringT::Replace](#replace)|Ersetzt angegebene Zeichen mit anderen Zeichen.|  
|[CStringT::ReverseFind](#reversefind)|Sucht ein Zeichen in einer größeren Zeichenfolge. beginnt am Ende.|  
|[CStringT::Right](#right)|Extrahiert den rechten Teil einer Zeichenfolge.|  
|[CStringT::SetSysString](#setsysstring)|Legt eine vorhandene `BSTR` -Objekt mit Daten aus einem `CStringT` Objekt.|  
|[CStringT::SpanExcluding](#spanexcluding)|Extrahiert Zeichen aus der Zeichenfolge, beginnend mit dem ersten Zeichen, die nicht in den Satz von Zeichen, die durch identifizierte `pszCharSet`.|  
|[CStringT::SpanIncluding](#spanincluding)|Extrahiert eine Teilzeichenfolge, die nur die Zeichen in einem Satz enthält.|  
|[CStringT::Tokenize](#tokenize)|Extrahiert angegebene Token in einer Zielzeichenfolge.|  
|[CStringT::Trim](#trim)|Entfernt alle führenden und nachgestellten Leerraumzeichen aus der Zeichenfolge.|  
|[CStringT::TrimLeft](#trimleft)|Entfernt führende Leerzeichen aus der Zeichenfolge.|  
|[CStringT::TrimRight](#trimright)|Entfernt nachfolgende Leerzeichen aus der Zeichenfolge.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator =](#operator_eq)|Weist einen neuen Wert zu einem `CStringT` Objekt.|  
|[CStringT::operator +](#operator_add)|Verkettet zwei Zeichenfolgen oder ein Zeichen und eine Zeichenfolge.|  
|[CStringT::operator +=](#operator_add_eq)|Verkettet eine neue Zeichenfolge am Ende einer vorhandenen Zeichenfolge.|  
|[CStringT::operator ==](#operator_eq_eq)|Bestimmt, ob zwei Zeichenfolgen logisch gleich sind.|  
|[CStringT::operator! =](#operator_neq)|Bestimmt, ob zwei Zeichenfolgen logisch nicht gleich sind.|  
|[CStringT::operator&lt;](#operator_lt)|Bestimmt, ob die Zeichenfolge auf der linken Seite des Operators kleiner als die Zeichenfolge auf der rechten Seite.|  
|[CStringT::operator&gt;](#operator_gt)|Bestimmt, ob die Zeichenfolge auf der linken Seite des Operators größer als die Zeichenfolge auf der rechten Seite ist.|  
|[CStringT::operator&lt;=](#operator_lt_eq)|Bestimmt, ob die Zeichenfolge auf der linken Seite des Operators kleiner oder gleich der Zeichenfolge auf der rechten Seite ist.|  
|[CStringT::operator&gt;=](#operator_gt_eq)|Bestimmt, ob die Zeichenfolge auf der linken Seite des Operators größer oder gleich der Zeichenfolge auf der rechten Seite ist.|  
  
## <a name="remarks"></a>Hinweise  
 `CStringT`erbt von [CSimpleStringT Klasse](../../atl-mfc-shared/reference/csimplestringt-class.md). Erweiterte Funktionen, wie z. B. die Bearbeitung von Zeichen, Sortierung und Suche von implementiert sind `CStringT`.  
  
> [!NOTE]
> `CStringT`Objekte können Ausnahmen auslösen. Dies tritt auf, wenn ein `CStringT` Objekt nicht mehr genügend Arbeitsspeicher aus irgendeinem Grund.  
  
 Ein `CStringT` -Objekt besteht aus einer Zeichenfolge variabler Länge. `CStringT`enthält Funktionen und Operatoren, die der Basic-ähnliche Syntax verwenden. Verkettung und Vergleichsoperatoren, zusammen mit vereinfachten Verwaltung stellen `CStringT` Objekte, die einfacher zu verwenden als normales Zeichen-Arrays.  
  
> [!NOTE]
>  Obwohl es möglich ist, erstellen Sie `CStringT` Instanzen, die enthalten eingebettete Null-Zeichen, wir empfehlen, vor. Aufrufen von Methoden und Operatoren für `CStringT` Objekte, die eingebetteten Null-Zeichen enthalten können zu unbeabsichtigte Ergebnissen führen.  
  
 Mit anderen Kombinationen von der `BaseType` und `StringTraits` Parameter `CStringT` Objekte kann sind die folgenden Typen sind vordefiniert wurden, die von den ATL-Bibliotheken.  
  
 Wenn eine ATL-Anwendung verwenden:  
  
 `CString`, `CStringA`, und `CStringW` werden exportiert, von der MFC-DLL (MFC90. (DLL), nicht vom Benutzer DLLs. Dies geschieht, um zu verhindern, dass `CStringT` aus wird mehrfach definiert.  
  
> [!NOTE]
>  Wenn Sie Linker beim Exportieren Fehler einer `CString`-abgeleitete Klasse von einer Erweiterung der MFC-DLL in Visual C++ .NET 2002 und die Lösung angewendet wie beschrieben in der Knowledge Base-Artikel "Verknüpfen von Fehlern bei der Sie Import CString-Derived Classes" (Q309801), sollten Sie den umgehungscode für dieses Problem zu, entfernen, da dies in Visual C++ .NET 2003 behoben wurde. Sie finden Knowledge Base-Artikeln der MSDN Library-CD-ROM oder auf [http://support.microsoft.com/support](http://support.microsoft.com/support).  
  
 Die folgenden Zeichenfolgen-Datentypen sind in MFC-basierten Anwendung verfügbar:  
  
|CStringT-Typ|Deklaration|  
|-------------------|-----------------|  
|`CStringA`|ANSI-Zeichen geben die Zeichenfolge mit der CRT-Unterstützung.|  
|`CStringW`|Ein Unicode-Zeichen geben die Zeichenfolge mit der CRT-Unterstützung.|  
|`CString`|ANSI- und Unicode-Zeichentypen mit CRT-Unterstützung.|  
  
 Die folgende Zeichenfolge Typen im stehen Projekte, in denen **ATL_CSTRING_NO_CRT** definiert ist:  
  
|CStringT-Typ|Deklaration|  
|-------------------|-----------------|  
|**CAtlStringA**|ANSI-Zeichen geben die Zeichenfolge ohne CRT-Unterstützung.|  
|**CAtlStringW**|Ein Unicode-Zeichen geben die Zeichenfolge ohne CRT-Unterstützung.|  
|**CAtlString**|ANSI- und Unicode-Zeichentypen ohne CRT-Unterstützung.|  
  
 Die folgende Zeichenfolge Typen im stehen Projekte, in denen **ATL_CSTRING_NO_CRT** ist nicht definiert:  
  
|CStringT-Typ|Deklaration|  
|-------------------|-----------------|  
|**CAtlStringA**|ANSI-Zeichen geben die Zeichenfolge mit der CRT-Unterstützung.|  
|**CAtlStringW**|Ein Unicode-Zeichen geben die Zeichenfolge mit der CRT-Unterstützung.|  
|**CAtlString**|ANSI- und Unicode-Zeichentypen mit CRT-Unterstützung.|  
  
 `CString`Objekte verfügen auch über die folgenden Merkmale:  
  
- `CStringT`Objekte können als Ergebnis der Verkettungsvorgänge vergrößert werden.  
  
- `CStringT`Führen Sie die Objekte "Wertsemantik". Stellen Sie sich ein `CStringT` Objekt als eine tatsächliche Zeichenfolge und nicht als ein Zeiger auf eine Zeichenfolge.  
  
-   Sie können problemlos ersetzen `CStringT` von Objekten für die `PCXSTR` Funktionsargumente.  
  
-   Benutzerdefinierte Speicherverwaltung für Zeichenfolgenpuffer. Weitere Informationen finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="cstringt-predefined-types"></a>CStringT vordefinierten Typen  
 Da `CStringT` Vorlagenargument verwendet, um Zeichen zu definieren (entweder [Wchar_t](../../c-runtime-library/standard-types.md) oder [Char](../../c-runtime-library/standard-types.md)) unterstützt, Parametertypen kompliziert sein Zeiten. Um dieses Problem zu vereinfachen, eine Reihe von vordefinierten Typen definiert und verwendet die `CStringT` Klasse. In der folgenden Tabelle sind die verschiedenen Typen aufgeführt:  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`XCHAR`|Ein einzelnes Zeichen (entweder `wchar_t` oder `char`) mit dem gleichen Zeichen als die `CStringT` Objekt.|  
|**YCHAR**|Ein einzelnes Zeichen (entweder `wchar_t` oder `char`) mit dem entgegengesetzten Zeichen als die `CStringT` Objekt.|  
|`PXSTR`|Ein Zeiger auf eine Zeichenfolge (entweder `wchar_t` oder `char`) mit dem gleichen Zeichen als die `CStringT` Objekt.|  
|**PYSTR**|Ein Zeiger auf eine Zeichenfolge (entweder `wchar_t` oder `char`) mit dem entgegengesetzten Zeichen als die `CStringT` Objekt.|  
|`PCXSTR`|Ein Zeiger auf eine **const** Zeichenfolge (entweder `wchar_t` oder `char`) mit dem gleichen Zeichen als die `CStringT` Objekt.|  
|**PCYSTR**|Ein Zeiger auf eine **const** Zeichenfolge (entweder `wchar_t` oder `char`) mit dem entgegengesetzten Zeichen als die `CStringT` Objekt.|  
  
> [!NOTE]
>  Code, der zuvor nicht dokumentierte Methoden verwendet `CString` (z. B. **AssignCopy**) ersetzt werden muss, mit Code, der die folgenden dokumentierten Methoden verwendet `CStringT` (z. B. `GetBuffer` oder `ReleaseBuffer`). Diese Methoden werden von geerbt `CSimpleStringT`.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)  
  
 `CStringT`  
  
## <a name="requirements"></a>Anforderungen  
  
|Header|Verwenden Sie für|  
|------------|-------------|  
|CStringT.h|Nur MFC-String-Objekten|  
|atlstr.h|MFC-fremde String-Objekten|  
  
##  <a name="a-nameallocsysstringa--cstringtallocsysstring"></a><a name="allocsysstring"></a>CStringT::AllocSysString  
 Ordnet eine Automatisierungskompatible-Zeichenfolge des Typs `BSTR` und kopiert den Inhalt der `CStringT` Objekt ein, einschließlich des abschließenden Null-Zeichens.  
  
```  
BSTR AllocSysString() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die neu zugeordneten Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 In MFC-Programmen eine [CMemoryException Klasse](../../mfc/reference/cmemoryexception-class.md) wird ausgelöst, wenn nicht genügend Arbeitsspeicher vorhanden ist. ATL-Programme eine [CAtlException](../../atl/reference/catlexception-class.md) ausgelöst. Diese Funktion wird normalerweise verwendet, um Zeichenfolgen für die Automatisierung zurückzugeben.  
  
 Häufig, wenn diese Zeichenfolge an eine COM-Funktion übergeben wird als [in]-Parameter, wird dadurch muss der Aufrufer die Zeichenfolge freigeben. Dies kann mithilfe [SysFreeString](http://msdn.microsoft.com/en-us/8f230ee3-5f6e-4cb9-a910-9c90b754dcd3), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Weitere Informationen finden Sie unter [Zuweisen von und Freigeben von Arbeitsspeicher für "BSTR"](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md).  
  
 Weitere Informationen über OLE-Zuordnungsfunktionen in Windows finden Sie unter [SysAllocString](http://msdn.microsoft.com/en-us/9e0437a2-9b4a-4576-88b0-5cb9d08ca29b) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CStringT::AllocSysString`.  
  
 [!code-cpp[NVC_ATLMFC_Utilities&#105;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]  
  
##  <a name="a-nameansitooema--cstringtansitooem"></a><a name="ansitooem"></a>CStringT::AnsiToOem  
 Konvertiert alle Zeichen in dieser `CStringT` Objekt aus dem ANSI-Zeichensatz in den OEM-Zeichensatz.  
  
```  
void AnsiToOem();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion ist nicht verfügbar wenn `_UNICODE` definiert ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#106;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]  
  
##  <a name="a-nameappendformata--cstringtappendformat"></a><a name="appendformat"></a>CStringT::AppendFormat  
 Fügt der formatierte Daten einer vorhandenen `CStringT` Objekt.  
  
```  
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```  
  
### <a name="parameters"></a>Parameter  
 `pszFormat`  
 Eine Zeichenfolge Steuerelement formatieren.  
  
 `nFormatID`  
 Die Zeichenfolge Ressourcenbezeichner, die die Format-Zeichenfolge enthält.  
  
 `argument`  
 Optionale Argumente.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion formatiert und fügt eine Abfolge von Zeichen und Werten in der `CStringT`. Jedes optionales Argument (sofern vorhanden) konvertiert und entsprechend der jeweiligen Formatangabe in angefügt `pszFormat` oder identifizierte Zeichenfolgenressource `nFormatID`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#107;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]  
  
##  <a name="a-namecollatea--cstringtcollate"></a><a name="collate"></a>CStringT::Collate  
 Vergleicht zwei Zeichenfolgen mithilfe der generische Textfunktion `_tcscoll`.  
  
```  
int Collate(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `psz`  
 Die andere Zeichenfolge für den Vergleich verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 NULL, wenn die Zeichenfolgen identisch sind, < 0="" if="" this=""> `CStringT` Objekt ist kleiner als `psz`, oder > 0, wenn diese `CStringT` -Objekt ist größer als `psz`.  
  
### <a name="remarks"></a>Hinweise  
 Die generische Textfunktion `_tcscoll`, definiert in TCHAR. H, ordnet entweder `strcoll`, `wcscoll`, oder `_mbscoll`, abhängig von den Zeichensatz, der zum Zeitpunkt der Kompilierung definiert ist. Jede Funktion führt eine Groß-/ Kleinschreibung der Zeichenfolgen entsprechend der Codepage derzeit verwenden. Weitere Informationen finden Sie unter [Strcoll, Wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).  
  
##  <a name="a-namecollatenocasea--cstringtcollatenocase"></a><a name="collatenocase"></a>CStringT::CollateNoCase  
 Vergleicht zwei Zeichenfolgen mithilfe der generische Textfunktion `_tcscoll`.  
  
```  
int CollateNoCase(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `psz`  
 Die andere Zeichenfolge für den Vergleich verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 0 (null), wenn die Zeichenfolgen identisch sind (Groß-/Kleinschreibung wird ignoriert), < 0="" if="" this=""> `CStringT` Objekt ist kleiner als `psz` (Groß-/Kleinschreibung wird ignoriert), oder > 0, wenn diese `CStringT` -Objekt ist größer als `psz` (Groß-/Kleinschreibung wird ignoriert).  
  
### <a name="remarks"></a>Hinweise  
 Die generische Textfunktion `_tcscoll`, definiert in TCHAR. H, ordnet entweder `stricoll`, `wcsicoll`, oder `_mbsicoll`, abhängig von den Zeichensatz, der zum Zeitpunkt der Kompilierung definiert ist. Jede Funktion führt die Groß-und Kleinschreibung der Zeichenfolgen, entsprechend der derzeit verwendeten Codepage. Weitere Informationen finden Sie unter [Strcoll, Wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#109;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]  
  
##  <a name="a-namecomparea--cstringtcompare"></a><a name="compare"></a>CStringT::Compare  
 Vergleicht zwei Zeichenfolgen (Groß-/Kleinschreibung wird beachtet).  
  
```  
int Compare(PCXSTR psz) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `psz`  
 Die andere Zeichenfolge für den Vergleich verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 NULL, wenn die Zeichenfolgen identisch sind, < 0="" if="" this=""> `CStringT` Objekt ist kleiner als `psz`, oder > 0, wenn diese `CStringT` -Objekt ist größer als `psz`.  
  
### <a name="remarks"></a>Hinweise  
 Die generische Textfunktion `_tcscmp`, definiert in TCHAR. H, ordnet entweder `strcmp`, `wcscmp`, oder `_mbscmp`, abhängig von den Zeichensatz, der zum Zeitpunkt der Kompilierung definiert ist. Jede Funktion führt eine Groß-/ Kleinschreibung der Zeichenfolgen und wird nicht vom Gebietsschema beeinflusst. Weitere Informationen finden Sie unter [Strcmp, Wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md).  
  
 Wenn die Zeichenfolge eingebettete NULL-Werte enthält, ist für Vergleichszwecke die Zeichenfolge als bei der ersten eingebettete Null-Zeichen abgeschnitten.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CStringT::Compare`.  
  
 [!code-cpp[NVC_ATLMFC_Utilities&#110;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]  
  
##  <a name="a-namecomparenocasea--cstringtcomparenocase"></a><a name="comparenocase"></a>CStringT::CompareNoCase  
 Vergleicht zwei Zeichenfolgen (ohne Berücksichtigung der Groß-und Kleinschreibung).  
  
```  
int CompareNoCase(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `psz`  
 Die andere Zeichenfolge für den Vergleich verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 0 (null), wenn die Zeichenfolgen identisch sind (Groß-/Kleinschreibung wird ignoriert), <0 if="" this=""></0> `CStringT` Objekt ist kleiner als `psz` (Groß-/Kleinschreibung wird ignoriert), oder >&0;, wenn diese `CStringT` -Objekt ist größer als `psz` (Groß-/Kleinschreibung wird ignoriert).  
  
### <a name="remarks"></a>Hinweise  
 Die generische Textfunktion `_tcsicmp`, definiert in TCHAR. H, ordnet entweder `_stricmp`, `_wcsicmp` oder `_mbsicmp`, abhängig von den Zeichensatz, der zum Zeitpunkt der Kompilierung definiert ist. Jede Funktion führt der Zeichenfolgen zwischen Groß-und Kleinschreibung. Hängt von der Vergleich der `LC_CTYPE` Aspekt des Gebietsschemas, aber nicht `LC_COLLATE`. Weitere Informationen finden Sie unter [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#111;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]  
  
##  <a name="a-namecstringta--cstringtcstringt"></a><a name="cstringt"></a>CStringT::CStringT  
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
 Ein Zeiger auf ein Array von Zeichen Länge `nLength`, nicht Null-terminiert.  
  
 `nLength`  
 Die Anzahl der Zeichen im `pch`.  
  
 `ch`  
 Ein einzelnes Zeichen.  
  
 `pszSrc`  
 Eine auf Null endende Zeichenfolge, die in diese kopiert werden `CStringT` Objekt.  
  
 `pStringMgr`  
 Ein Zeiger auf den Speichermanager für die `CStringT` Objekt. Weitere Informationen zu `IAtlStringMgr` und Verwaltung des Arbeitsspeichers für `CStringT`, finden Sie unter [Speicherverwaltung mit CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
 `strSrc`  
 Eine vorhandene `CStringT` Objekt in diese kopiert werden `CStringT` Objekt. Weitere Informationen zu `CThisString` und `CThisSimpleString`, finden Sie im Abschnitt "Hinweise".  
  
 `varSrc`  
 Ein variant-Objekt in diese kopiert werden `CStringT` Objekt.  
  
 `BaseType`  
 Der Typ der String-Klasse. Einer der folgenden Werte ist möglich:  
  
 `char`(für ANSI-Zeichenfolgen).  
  
 `wchar_t`(für Unicode-Zeichenfolgen).  
  
 `TCHAR`(nach ANSI- und Unicode-Zeichenfolgen).  
  
 `bMFCDLL`  
 Boolescher Wert, der angibt, ob das Projekt eine MFC-DLL (TRUE) oder nicht (FALSE).  
  
 `SystemString`  
 Muss `System::String`, und das Projekt muss mit/CLR kompiliert werden.  
  
 `pString`  
 Ein Handle für ein `CStringT` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Da die Konstruktoren die Eingabedaten in neuen reservierten Speicher kopieren, sollten Sie bedenken, dass der Speicher Ausnahmen führen können. Beachten Sie, dass einige dieser Konstruktoren als Funktionen fungieren. Dies können Sie ersetzen, z. B. ein `LPTSTR` , in dem eine `CStringT` -Objekt wird erwartet.  
  
- `CStringT`( `LPCSTR` `lpsz` ): Erstellt eine Unicode `CStringT` aus einer ANSI-Zeichenfolge. Sie können diesen Konstruktor auch verwenden, beim Laden einer Zeichenfolgenressource wie im folgenden Beispiel gezeigt.  
  
- `CStringT(``LPCWSTR` `lpsz` ): Erstellt eine `CStringT` eine Unicode-Zeichenfolge.  
  
- `CStringT`( `const unsigned char*` `psz` ): Ermöglicht das Erstellen einer `CStringT` von einem Zeiger auf `unsigned char`.  
  
> [!NOTE]
>  Definieren der **_CSTRING_DISABLE_NARROW_WIDE_CONVERSION** Makro so deaktivieren Sie die implizite Konvertierung zwischen [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] und [!INCLUDE[TLA#tla_unicode](../../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] Zeichenfolgen. Das Makro schließt aus Kompilierung-Konstruktoren, die Konvertierung zu unterstützen.  
  
 Beachten Sie, dass die `strSrc` Parameter kann entweder ein `CStringT` oder `CThisSimpleString` Objekt. Für `CStringT`, verwenden Sie den Standard-Instanziierungen ( `CString`, `CStringA`, oder `CStringW`); `CThisSimpleString`, verwenden Sie eine `this` Zeiger. `CThisSimpleString`deklariert eine Instanz der [CSimpleStringT Klasse](../../atl-mfc-shared/reference/csimplestringt-class.md), also eine kleinere-Klasse mit weniger integrierten Funktionen als die `CStringT` Klasse.  
  
 Die Überladungsoperator `CSimpleStringT<>&()` erstellt eine `CStringT` -Objekt aus einem `CSimpleStringT` Deklaration.  
  
> [!NOTE]
>  Obwohl es möglich ist, erstellen Sie `CStringT` Instanzen, die enthalten eingebettete Null-Zeichen, wir empfehlen, vor. Aufrufen von Methoden und Operatoren für `CStringT` Objekte, die eingebetteten Null-Zeichen enthalten können zu unbeabsichtigte Ergebnissen führen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#112;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]  
  
##  <a name="a-namedtorcstringta--cstringtcstringt"></a><a name="_dtorcstringt"></a>CStringT:: ~ CStringT  
 Zerstört das `CStringT`-Objekt.  
  
```  
~CStringT() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Zerstört das `CStringT`-Objekt.  
  
##  <a name="a-namedeletea--cstringtdelete"></a><a name="delete"></a>CStringT::Delete  
 Löscht ein oder mehrere Zeichen aus einer Zeichenfolge, die das Zeichen am angegebenen Index ab.  
  
```  
int Delete(int iIndex, int nCount = 1);
```  
  
### <a name="parameters"></a>Parameter  
 `iIndex`  
 Der nullbasierte Index des ersten Zeichens in der `CStringT` zu löschenden Objekts.  
  
 `nCount`  
 Die Anzahl der zu entfernenden Zeichen enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der die geänderte Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `nCount` ist länger als die Zeichenfolge, die den Rest der Zeichenfolge entfernt werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#113;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_8.cpp)]  
  
```Output  
Before: Soccer is best,
    but hockey is quicker!  
After: Soccer best,
    but hockey is quicker!  
```  
  
##  <a name="a-namefinda--cstringtfind"></a><a name="find"></a>CStringT::Find  
 Die erste Übereinstimmung eines Zeichens oder einer Teilzeichenfolge dieser Zeichenfolge gesucht.  
  
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
 Ein einzelnes Zeichen zu suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des ersten Zeichens in dieser `CStringT` -Objekt, das bzw. die angeforderte Unterzeichenfolge entspricht; -1, wenn das Zeichen oder die Teilzeichenfolge nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion wird überladen, um sowohl einzelnen Zeichen akzeptieren (vergleichbar mit der Funktion zur Laufzeit `strchr`) und Zeichenfolgen (ähnlich wie `strstr`).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#114;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]  
  
##  <a name="a-namefindoneofa--cstringtfindoneof"></a><a name="findoneof"></a>CStringT::FindOneOf  
 Sucht diese Zeichenfolge für das erste Zeichen, das jedem Zeichen in enthaltenen `pszCharSet`.  
  
```  
int FindOneOf(PCXSTR pszCharSet) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszCharSet`  
 Eine Zeichenfolge, Zeichen für den Abgleich.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des ersten Zeichens in dieser Zeichenfolge, die auch in `pszCharSet`;&1;, wenn keine Übereinstimmung vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Sucht das erste Vorkommen der Zeichen im `pszCharSet`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#115;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]  
  
##  <a name="a-nameformata--cstringtformat"></a><a name="format"></a>CStringT::Format  
 Schreibt formatierte Daten in eine `CStringT` in der gleichen Weise wie [Sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) Daten als Array im C-Format Zeichen formatiert.  
  
```  
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```  
  
### <a name="parameters"></a>Parameter  
 `nFormatID`  
 Die Zeichenfolge Ressourcenbezeichner, die die Format-Zeichenfolge enthält.  
  
 `pszFormat`  
 Eine Zeichenfolge Steuerelement formatieren.  
  
 `argument`  
 Optionale Argumente.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion formatiert und speichert eine Reihe von Zeichen und Werten in der `CStringT`. Jedes optionales Argument (sofern vorhanden) konvertiert und entsprechend der jeweiligen Formatangabe in output `pszFormat` oder identifizierte Zeichenfolgenressource `nFormatID`.  
  
 Der Aufruf schlägt fehl, wenn das String-Objekt selbst als Parameter an angeboten wird `Format`. Im folgende Code wird z. B. zu unvorhersehbaren Ergebnissen führen:  
  
 [!code-cpp[NVC_ATLMFC_Utilities Nr.&116;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]  
  
 Weitere Informationen finden Sie unter [Format Specification Syntax: printf and wprintf Functions (Syntax der Formatangabe: printf- und wprintf-Funktionen)](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#117;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]  
  
##  <a name="a-nameformatmessagea--cstringtformatmessage"></a><a name="formatmessage"></a>CStringT::FormatMessage  
 Formatiert eine Meldungszeichenfolge.  
  
```  
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```  
  
### <a name="parameters"></a>Parameter  
 `nFormatID`  
 Der Ressourcenbezeichner des Zeichenfolge, die den unformatierten Nachrichtentext enthält.  
  
 `pszFormat`  
 Verweist auf die Format-Zeichenfolge. Es werden fügt überprüft und entsprechend formatiert. Die Formatzeichenfolge ähnelt Laufzeitfunktion `printf`-Formatzeichenfolgen formatieren, außer für die Parameter in einer beliebigen Reihenfolge eingefügt werden können.  
  
 `argument`  
 Optionale Argumente.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion erfordert als Eingabe eine Nachrichtendefinition. Der Meldungsdefinition richtet sich nach `pszFormat` oder identifizierte Zeichenfolgenressource `nFormatID`. Die Funktion kopiert die formatierte Nachrichtentext für die `CStringT` Verarbeitung eines anderen, eingebetteten Objekt einfügen Sequenzen angefordert.  
  
> [!NOTE]
> `FormatMessage`versucht, den Systemspeicher für die neu formatierten Zeichenfolge reservieren. Wenn dieser Versuch fehlschlägt, wird automatisch eine Arbeitsspeicher-Ausnahme ausgelöst.  
  
 Jede Einfügung muss einen entsprechenden Parameter Folgendes haben die `pszFormat` oder `nFormatID` Parameter. In den Nachrichtentext werden mehrere Escapesequenzen für dynamische Formatierung der Nachricht unterstützt. Weitere Informationen finden Sie unter Windows [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) -Funktion in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#118;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]  
  
##  <a name="a-nameformatmessageva--cstringtformatmessagev"></a><a name="formatmessagev"></a>CStringT::FormatMessageV  
 Formatiert eine Zeichenfolge mit einer Liste variabler Argumente.  
  
```  
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```  
  
### <a name="parameters"></a>Parameter  
 `pszFormat`  
 Verweist auf die Format-Zeichenfolge. Es werden fügt überprüft und entsprechend formatiert. Die Formatzeichenfolge ähnelt Laufzeitfunktion `printf`-Formatzeichenfolgen formatieren, außer für die Parameter in einer beliebigen Reihenfolge eingefügt werden können.  
  
 `pArgList`  
 Ein Zeiger auf eine Liste von Argumenten.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion erfordert als Eingabe eine Nachrichtendefinition durch bestimmt `pszFormat`. Die Funktion kopiert die formatierte Nachricht und eine Variable Liste von Argumenten, die die `CStringT` Verarbeitung eines anderen, eingebetteten Objekt einfügen Sequenzen angefordert.  
  
> [!NOTE]
> `FormatMessageV`Aufrufe [CStringT::FormatMessage](#formatmessage), die versucht, den Systemspeicher für die neu formatierten Zeichenfolge zugeordnet werden. Wenn dieser Versuch fehlschlägt, wird automatisch eine Arbeitsspeicher-Ausnahme ausgelöst.  
  
 Weitere Informationen finden Sie unter Windows [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) -Funktion in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameformatva--cstringtformatv"></a><a name="formatv"></a>CStringT::FormatV  
 Formatiert eine Zeichenfolge mit einer Liste variabler Argumente.  
  
```  
void FormatV(PCXSTR pszFormat, va_list args);
```  
  
### <a name="parameters"></a>Parameter  
 `pszFormat`  
 Verweist auf die Format-Zeichenfolge. Es werden fügt überprüft und entsprechend formatiert. Die Formatzeichenfolge ähnelt Laufzeitfunktion `printf`-Formatzeichenfolgen formatieren, außer für die Parameter in einer beliebigen Reihenfolge eingefügt werden können.  
  
 `args`  
 Ein Zeiger auf eine Liste von Argumenten.  
  
### <a name="remarks"></a>Hinweise  
 Schreibt eine formatierte Zeichenfolge und eine Variable Liste von Argumenten, die eine `CStringT` Zeichenfolge in der gleichen Weise wie `vsprintf_s` Daten als Array im C-Format Zeichen formatiert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#119;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities&#120;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]  
  
##  <a name="a-namegetenvironmentvariablea--cstringtgetenvironmentvariable"></a><a name="getenvironmentvariable"></a>CStringT::GetEnvironmentVariable  
 Die Zeichenfolge wird auf den Wert der angegebenen Umgebungsvariablen festgelegt.  
  
```  
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```  
  
### <a name="parameters"></a>Parameter  
 `pszVar`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die der Umgebungsvariablen angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Ruft den Wert der angegebenen Variablen in dem Umgebungsblock des aufrufenden Prozesses ab. Der Wert ist in Form einer Null-terminierte Zeichenfolge von Zeichen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#121;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]  
  
##  <a name="a-nameinserta--cstringtinsert"></a><a name="insert"></a>CStringT::Insert  
 Fügt ein einzelnes Zeichen oder eine Teilzeichenfolge am angegebenen Index in der Zeichenfolge.  
  
```  
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```  
  
### <a name="parameters"></a>Parameter  
 `iIndex`  
 Der Index des Zeichens vor dem Einfügen stattfinden soll.  
  
 `psz`  
 Ein Zeiger auf die Teilzeichenfolge, eingefügt werden soll.  
  
 `ch`  
 Das einzufügende Zeichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der die geänderte Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Die `iIndex` Parameter identifiziert die erste Zeichen, das verschoben wird, um Platz für das Zeichen oder eine Teilzeichenfolge. Wenn `nIndex` NULL ist, wird vor der gesamten Zeichenfolge werden. Wenn `nIndex` ist größer als die Länge der Zeichenfolge, die Funktion die vorhandene Zeichenfolge verketten wird und das neue Material bereitgestellt wird, entweder durch `ch` oder `psz`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#122;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]  
  
##  <a name="a-namelefta--cstringtleft"></a><a name="left"></a>CStringT::Left  
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
 [!code-cpp[NVC_ATLMFC_Utilities&#123;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]  
  
##  <a name="a-nameloadstringa--cstringtloadstring"></a><a name="loadstring"></a>CStringT::LoadString  
 Liest eine Zeichenfolgenressource Windows, identifizierten `nID`, in eine vorhandene `CStringT` Objekt.  
  
```  
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `hInstance`  
 Ein Handle für die Instanz des Moduls.  
  
 `nID`  
 Eine Windows-Zeichenfolge-Ressourcen-ID  
  
 `wLanguageID`  
 Die Sprache der Zeichenfolgenressource.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Ladevorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Lädt die Zeichenfolgenressource ( `nID`) aus dem angegebenen Modul ( `hInstance`) mit der angegebenen Sprache ( `wLanguage`).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#124;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]  
  
##  <a name="a-namemakelowera--cstringtmakelower"></a><a name="makelower"></a>CStringT::MakeLower  
 Konvertiert die `CStringT` Objekt in eine Zeichenfolge aus Kleinbuchstaben.  
  
```  
CStringT& MakeLower();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die resultierende Zeichenfolge aus Kleinbuchstaben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#125;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]  
  
##  <a name="a-namemakereversea--cstringtmakereverse"></a><a name="makereverse"></a>CStringT::MakeReverse  
 Kehrt die Reihenfolge der Zeichen in der `CStringT` Objekt.  
  
```  
CStringT& MakeReverse();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die resultierende umgekehrt Zeichenfolge.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#126;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]  
  
##  <a name="a-namemakeuppera--cstringtmakeupper"></a><a name="makeupper"></a>CStringT::MakeUpper  
 Konvertiert die `CStringT` Objekt, das eine Zeichenfolge in Großbuchstaben.  
  
```  
CStringT& MakeUpper();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die resultierende Zeichenfolge in Großbuchstaben.  
  
### <a name="remarks"></a>Hinweise  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[127 NVC_ATLMFC_Utilities](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]  
  
##  <a name="a-namemida--cstringtmid"></a><a name="mid"></a>CStringT::Mid  
 Extrahiert eine Teilzeichenfolge mit der Länge `nCount` Zeichen aus diesem `CStringT` -Objekt, beginnend an der Position `iFirst` (nullbasiert).  
  
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
 Die Funktion gibt eine Kopie der extrahierten Teilzeichenfolge zurück. `Mid`ähnelt der grundlegenden Mid-Funktion (außer, dass Indizes in Basic&1;-basiert sind).  
  
 Für Mehrbyte-Zeichensätzen (MBCS) setzt `nCount` bezieht sich auf jedes 8-Bit-Zeichen, d. h. ein und die nachfolgenden Byte in einem multibyte-Zeichen als zwei Zeichen gezählt werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#128;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]  
  
##  <a name="a-nameoemtoansia--cstringtoemtoansi"></a><a name="oemtoansi"></a>CStringT::OemToAnsi  
 Konvertiert alle Zeichen in dieser `CStringT` Objekt aus dem OEM-Zeichensatz in den ANSI-Zeichensatz.  
  
```  
void OemToAnsi();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist nicht verfügbar wenn `_UNICODE` definiert ist.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CStringT::AnsiToOem](#ansitooem).  
  
##  <a name="a-nameoperatoradda--cstringtoperator-"></a><a name="operator_add"></a>CStringT::operator +  
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
 Ein ANSI- oder Unicode-Zeichen mit einer Zeichenfolge verkettet.  
  
 `ch2`  
 Ein ANSI- oder Unicode-Zeichen mit einer Zeichenfolge verkettet.  
  
 `str1`  
 Ein `CStringT` mit einer Zeichenfolge oder ein Zeichen zu verketten.  
  
 `str2`  
 Ein `CStringT` mit einer Zeichenfolge oder ein Zeichen zu verketten.  
  
 `psz1`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge mit einer Zeichenfolge oder ein Zeichen zu verketten.  
  
 `psz2`  
 Ein Zeiger auf eine Zeichenfolge mit einer Zeichenfolge oder ein Zeichen zu verketten.  
  
### <a name="remarks"></a>Hinweise  
 Es gibt sieben Überladung der `CStringT::operator+` Funktion. Die erste Version verkettet zwei vorhandene `CStringT` Objekte. Die nächsten beiden Verketten einer `CStringT` Objekt und eine Null-terminierte Zeichenfolge. Die nächsten beiden Verketten einer `CStringT` Objekt und ANSI-Zeichen. Die letzten beiden Verketten einer `CStringT` -Objekt und ein Unicode-Zeichen.  
  
> [!NOTE]
>  Obwohl es möglich ist, erstellen Sie `CStringT` Instanzen, die enthalten eingebettete Null-Zeichen, wir empfehlen, vor. Aufrufen von Methoden und Operatoren für `CStringT` Objekte, die eingebetteten Null-Zeichen enthalten können zu unbeabsichtigte Ergebnissen führen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#140;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]  
  
##  <a name="a-nameoperatoraddeqa--cstringtoperator-"></a><a name="operator_add_eq"></a>CStringT::operator +=  
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
 Ein variant-Objekt, die mit dieser Zeichenfolge verkettet.  
  
 `ch`  
 Ein ANSI- oder Unicode-Zeichen mit einer Zeichenfolge verkettet.  
  
 `pszSrc`  
 Ein Zeiger auf die ursprüngliche Zeichenfolge verkettet werden.  
  
 `strSrc`  
 Ein `CStringT` , die mit dieser Zeichenfolge verkettet.  
  
### <a name="remarks"></a>Hinweise  
 Der Operator akzeptiert ein anderes `CStringT` Objekt, einen Zeichenzeiger oder ein einzelnes Zeichen. Sie sollten sich bewusst sein, dass der Speicher Ausnahmen können auftreten, wenn Sie diese Verkettungsoperator verwenden, da es sich bei neuer Speicher für diese hinzugefügten Zeichen zugewiesen werden kann `CStringT` Objekt.  
  
 Informationen zu `CThisSimpleString`, finden Sie im Abschnitt "Hinweise" [CStringT::CStringT](#cstringt).  
  
> [!NOTE]
>  Obwohl es möglich ist, erstellen Sie `CStringT` Instanzen, die enthalten eingebettete Null-Zeichen, wir empfehlen, vor. Aufrufen von Methoden und Operatoren für `CStringT` Objekte, die eingebetteten Null-Zeichen enthalten können zu unbeabsichtigte Ergebnissen führen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#141;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]  
  
##  <a name="a-nameoperatoreqeqa--cstringtoperator-"></a><a name="operator_eq_eq"></a>CStringT::operator ==  
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
 Ein ANSI- oder Unicode-Zeichen für den Vergleich.  
  
 `ch2`  
 Ein ANSI- oder Unicode-Zeichen für den Vergleich.  
  
 `str1`  
 Ein `CStringT` für den Vergleich.  
  
 `str2`  
 Ein `CStringT` für den Vergleich.  
  
 `psz1`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.  
  
 `psz2`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.  
  
### <a name="remarks"></a>Hinweise  
 Testet, ob eine Zeichenfolge oder ein Zeichen auf der linken Seite eine Zeichenfolge oder ein Zeichen auf der rechten Seite gleich ist, und gibt TRUE oder FALSE entsprechend zurück.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#142;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]  
  
##  <a name="a-nameoperatorneqa--cstringtoperator-"></a><a name="operator_neq"></a>CStringT::operator! =  
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
 Ein ANSI- oder Unicode-Zeichen mit einer Zeichenfolge verkettet.  
  
 `ch2`  
 Ein ANSI- oder Unicode-Zeichen mit einer Zeichenfolge verkettet.  
  
 `str1`  
 Ein `CStringT` für den Vergleich.  
  
 `str2`  
 Ein `CStringT` für den Vergleich.  
  
 `psz1`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.  
  
 `psz2`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.  
  
### <a name="remarks"></a>Hinweise  
 Testet, ob eine Zeichenfolge oder ein Zeichen auf der linken Seite ungleich in eine Zeichenfolge oder ein Zeichen auf der rechten Seite ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#143;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]  
  
##  <a name="a-nameoperatorlta--cstringtoperator-lt"></a><a name="operator_lt"></a>CStringT::operator&lt;  
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
 [!code-cpp[NVC_ATLMFC_Utilities&#144;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]  
  
##  <a name="a-nameoperatorgta--cstringtoperator-gt"></a><a name="operator_gt"></a>CStringT::operator&gt;  
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
 [!code-cpp[NVC_ATLMFC_Utilities&#145;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]  
  
##  <a name="a-nameoperatorlteqa--cstringtoperator-lt"></a><a name="operator_lt_eq"></a>CStringT::operator&lt;=  
 Bestimmt, ob die Zeichenfolge auf der linken Seite des Operators kleiner oder gleich der Zeichenfolge auf der rechten Seite ist.  
  
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
 [!code-cpp[NVC_ATLMFC_Utilities&#146;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]  
  
##  <a name="a-nameoperatorgteqa--cstringtoperator-gt"></a><a name="operator_gt_eq"></a>CStringT::operator&gt;=  
 Bestimmt, ob die Zeichenfolge auf der linken Seite des Operators größer oder gleich der Zeichenfolge auf der rechten Seite ist.  
  
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
 [!code-cpp[NVC_ATLMFC_Utilities&#147;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]  
  
##  <a name="a-nameremovea--cstringtremove"></a><a name="remove"></a>CStringT::Remove  
 Alle Instanzen des angegebenen Zeichens entfernt aus der Zeichenfolge.  
  
```  
int Remove(XCHAR chRemove);
```  
  
### <a name="parameters"></a>Parameter  
 `chRemove`  
 Das Zeichen aus einer Zeichenfolge entfernt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeichen aus der Zeichenfolge entfernt. NULL, wenn die Zeichenfolge nicht geändert wird.  
  
### <a name="remarks"></a>Hinweise  
 Vergleiche für das Zeichen, Groß-/Kleinschreibung unterschieden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#129;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]  
  
##  <a name="a-namereplacea--cstringtreplace"></a><a name="replace"></a>CStringT::Replace  
 Es gibt zwei Versionen des `Replace`. Die erste Version ersetzt eine oder mehrere Kopien einer Teilzeichenfolge durch eine andere Teilzeichenfolge. Beide Teilzeichenfolgen sind Null-terminiert. Die zweite Version ersetzt eine oder mehrere Kopien eines Zeichens durch ein anderes Zeichen. Beide Versionen arbeiten mit Zeichendaten `CStringT`.  
  
```  
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```  
  
### <a name="parameters"></a>Parameter  
 `pszOld`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge zu ersetzen durch `pszNew`.  
  
 `pszNew`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die ersetzt `pszOld`.  
  
 `chOld`  
 Das Zeichen, das durch ersetzt `chNew`.  
  
 `chNew`  
 Ersetzen von Zeichen `chOld`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl Instanzen ersetzt das Zeichen oder Substring oder&0; (null) zurück, wenn die Zeichenfolge nicht geändert wird.  
  
### <a name="remarks"></a>Hinweise  
 `Replace`die Länge der Zeichenfolge kann geändert werden, da `pszNew` und `pszOld` müssen nicht dieselbe Länge aufweisen und mehrere Kopien der alten Teilzeichenfolge in das neue Projekt geändert werden können. Die Funktion führt die Groß-/Kleinschreibung beachtet.  
  
 Beispiele für `CStringT` Instanzen sind `CString`, `CStringA`, und `CStringW`.  
  
 Für `CStringA`, `Replace` arbeitet mit ANSI oder Multibytezeichen (MBCS). Für `CStringW`, `Replace` arbeitet mit Breitzeichen.  
  
 Für `CString`, zum Zeitpunkt der Kompilierung der Zeichendatentyp ausgewählt ist, basierend auf, ob die Konstanten in der folgenden Tabelle definiert sind.  
  
|Definierte Konstante|Character-Datentyp|  
|----------------------|-------------------------|  
|`_UNICODE`|Breitzeichen|  
|`_MBCS`|Multi-Byte-Zeichen|  
|Weder noch|Single-Byte-Zeichen|  
|Beides|Nicht definiert|  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#200;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]  
  
##  <a name="a-namereversefinda--cstringtreversefind"></a><a name="reversefind"></a>CStringT::ReverseFind  
 Sucht das `CStringT` -Objekt für die letzte Übereinstimmung eines Zeichens.  
  
```  
int ReverseFind(XCHAR ch) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ch`  
 Das zu suchende Zeichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des letzten Zeichens in dieser `CStringT` -Objekt, das entspricht der angeforderten Zeichen, oder -1, wenn das Zeichen nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion ist vergleichbar mit der Funktion zur Laufzeit `strrchr`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#130;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]  
  
##  <a name="a-namerighta--cstringtright"></a><a name="right"></a>CStringT::Right  
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
 Wenn `nCount` die Zeichenfolgenlänge überschreitet, wird die gesamte Zeichenfolge extrahiert. `Right`wird ähnlich wie der grundlegende `Right` -Funktion (außer, dass Indizes in Basic nullbasiert sind).  
  
 Für Mehrbyte-Zeichensätzen (MBCS) setzt `nCount` bezieht sich auf jedes 8-Bit-Zeichen, d. h. ein und die nachfolgenden Byte in einem multibyte-Zeichen als zwei Zeichen gezählt werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#131;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]  
  
##  <a name="a-namesetsysstringa--cstringtsetsysstring"></a><a name="setsysstring"></a>CStringT::SetSysString  
 Zuordnet der `BSTR` auf den `pbstr` und kopiert den Inhalt der `CStringT` -Objekts ein, einschließlich der `NULL` Zeichen.  
  
```  
BSTR SetSysString(BSTR* pbstr) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `pbstr`  
 Ein Zeiger auf eine Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Die neue Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Abhängig vom Inhalt der `CStringT` -Objekt, das den Wert des der `BSTR` verweist `pbstr` ändern können. Die Funktion löst einen `CMemoryException` Wenn nicht genügend Arbeitsspeicher vorhanden ist.  
  
 Diese Funktion wird normalerweise verwendet, um den Wert von Zeichenfolgen, die als Verweis übergeben wird, für die Automatisierung ändern.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#132;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]  
  
##  <a name="a-namespanexcludinga--cstringtspanexcluding"></a><a name="spanexcluding"></a>CStringT::SpanExcluding  
 Extrahiert Zeichen aus der Zeichenfolge, beginnend mit dem ersten Zeichen, die nicht in den Satz von Zeichen, die durch identifizierte `pszCharSet`.  
  
```  
CStringT SpanExcluding(PCXSTR pszCharSet) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `pszCharSet`  
 Eine Zeichenfolge, die als eine Reihe von Zeichen interpretiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Teilzeichenfolge, die Zeichen in der Zeichenfolge enthält, die nicht `pszCharSet`, mit dem ersten Zeichen in der Zeichenfolge und endet mit dem ersten Zeichen in der Zeichenfolge, die auch in gefunden `pszCharSet` (mit dem ersten Zeichen in der Zeichenfolge und bis zum, jedoch ohne das erste Zeichen in der Zeichenfolge, die gefunden wird, also beginnend `pszCharSet`). Wird die gesamte Zeichenfolge zurückgegeben, wenn kein Zeichen in `pszCharSet` befindet sich in der Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 `SpanExcluding`extrahiert und gibt alle Zeichen, die vor das erste Vorkommen eines Zeichens aus `pszCharSet` (das heißt, das Zeichen `pszCharSet` und alle in der Zeichenfolge mit folgenden Zeichen nicht zurückgegeben werden). Wenn keine Zeichen aus `pszCharSet` befindet sich in der Zeichenfolge anschließend `SpanExcluding` die gesamte Zeichenfolge zurückgegeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#133;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]  
  
##  <a name="a-namespanincludinga--cstringtspanincluding"></a><a name="spanincluding"></a>CStringT::SpanIncluding  
 Extrahiert Zeichen aus der Zeichenfolge, beginnend mit dem ersten Zeichen, die in den Satz von Zeichen, die durch identifizierte sind `pszCharSet`.  
  
```  
CStringT SpanIncluding(PCXSTR pszCharSet) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `pszCharSet`  
 Eine Zeichenfolge, die als eine Reihe von Zeichen interpretiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Teilzeichenfolge, die Zeichen in der Zeichenfolge, die in enthält `pszCharSet`, mit dem ersten Zeichen in der Zeichenfolge beginnt und endet, wenn ein Zeichen in der Zeichenfolge gefunden wird, der nicht `pszCharSet.``SpanIncluding` eine leere Zeichenfolge zurückgibt, ist das erste Zeichen in der Zeichenfolge nicht in der angegebenen Menge.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das erste Zeichen der Zeichenfolge nicht in den Zeichensatz ist `SpanIncluding` eine leere Zeichenfolge zurückgegeben. Andernfalls wird eine Folge von aufeinander folgenden Zeichen, die in der Menge zurückgegeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#134;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]  
  
##  <a name="a-nametokenizea--cstringttokenize"></a><a name="tokenize"></a>CStringT::Tokenize  
 Sucht das nächste Token in einer Zielzeichenfolge  
  
```  
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `pszTokens`  
 Eine Zeichenfolge mit token-Trennzeichen. Die Reihenfolge der diese Trennzeichen ist nicht wichtig.  
  
 `iStart`  
 Der nullbasierte Index, um die Suche zu starten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CStringT` Objekt, das den aktuellen Tokenwert enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die `Tokenize` -Funktion sucht das nächste Token in der Zielzeichenfolge. Der Satz von Zeichen im `pszTokens` gibt mögliche Trennzeichen des Tokens gefunden werden. Bei jedem Aufruf von `Tokenize` die Funktion beginnt bei `iStart`, überspringt führende Trennzeichen und gibt ein `CStringT` -Objekt, enthält das aktuelle Token, das die Zeichenfolge von Zeichen bis zum nächsten Trennzeichen ist. Der Wert des `iStart` wird aktualisiert, um die Position nach das letzte Trennzeichen oder -1, wenn das Ende der Zeichenfolge erreicht wurde. Weitere Token können geholt werden den Rest der Zielzeichenfolge durch eine Reihe von Aufrufen an `Tokenize`mit `iStart` zu verfolgen, wo in der Zeichenfolge das nächste Token gelesen werden. Wenn keine Token mehr vorhanden sind die Funktion eine leere Zeichenfolge zurück und `iStart` wird auf-1 festgelegt.  
  
 Im Gegensatz zu der CRT Verarbeitungsmethode Funktionen wie [Strtok_s, _strtok_s_l, Wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md), `Tokenize` die Zielzeichenfolge nicht geändert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#135;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]  
  
### <a name="remarks"></a>Hinweise  
 Die Ausgabe dieses Beispiels lautet wie folgt:  
  
 `Resulting Token: First`  
  
 `Resulting Token: Second`  
  
 `Resulting Token: Third`  
  
##  <a name="a-nametrima--cstringttrim"></a><a name="trim"></a>CStringT::Trim  
 Entfernt führende und nachfolgende Zeichen aus der Zeichenfolge.  
  
```  
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```  
  
### <a name="parameters"></a>Parameter  
 `chTarget`  
 Das Ziel Zeichen gekürzt.  
  
 `pszTargets`  
 Ein Zeiger auf eine Zeichenfolge mit dem Ziel Zeichen gekürzt werden. Alle führenden und nachgestellten Vorkommen der Zeichen im `pszTarget` abgeschnitten aus der `CStringT` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die zugeschnittene Zeichenfolge zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Entfernt alle führende und nachgestellte Vorkommen eines der folgenden:  
  
-   Die durch angegebene Zeichen`chTarget.`  
  
-   Alle Zeichen in der angegebenen Zeichenfolge gefunden`pszTargets.`  
  
-   Leerzeichen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#136;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]  
  
### <a name="remarks"></a>Hinweise  
 Die Ausgabe dieses Beispiels lautet wie folgt:  
  
 `Before: "******Soccer is best, but liquor is quicker!!!!!"`  
  
 `After : "Soccer is best, but liquor is quicker"`  
  
##  <a name="a-nametrimlefta--cstringttrimleft"></a><a name="trimleft"></a>CStringT::TrimLeft  
 Entfernt die führenden Zeichen aus der Zeichenfolge.  
  
```  
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```  
  
### <a name="parameters"></a>Parameter  
 `chTarget`  
 Das Ziel Zeichen gekürzt.  
  
 `pszTargets`  
 Ein Zeiger auf eine Zeichenfolge mit dem Ziel Zeichen gekürzt werden. Alle nachgestellten Vorkommen der Zeichen im `pszTarget` abgeschnitten aus der `CStringT` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die resultierende zugeschnittene Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Entfernt alle führende und nachgestellte Vorkommen eines der folgenden:  
  
-   Die durch angegebene Zeichen`chTarget.`  
  
-   Alle Zeichen in der angegebenen Zeichenfolge gefunden`pszTargets.`  
  
-   Leerzeichen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#137;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]  
  
##  <a name="a-nametrimrighta--cstringttrimright"></a><a name="trimright"></a>CStringT::TrimRight  
 Schneidet die nachgestellten Zeichen aus der Zeichenfolge.  
  
```  
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```  
  
### <a name="parameters"></a>Parameter  
 `chTarget`  
 Das Ziel Zeichen gekürzt.  
  
 `pszTargets`  
 Ein Zeiger auf eine Zeichenfolge mit dem Ziel Zeichen gekürzt werden. Alle nachgestellten Vorkommen der Zeichen im `pszTarget` abgeschnitten aus der `CStringT` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die `CStringT` -Objekt, das die zugeschnittene Zeichenfolge enthält.  
  
### <a name="remarks"></a>Hinweise  
 Entfernt nachfolgende Vorkommen eines der folgenden:  
  
-   Die durch angegebene Zeichen`chTarget.`  
  
-   Alle Zeichen in der angegebenen Zeichenfolge gefunden`pszTargets.`  
  
-   Leerzeichen.  
  
 Die `CStringT& TrimRight(XCHAR chTarget)` Version als Zeichenparameter akzeptiert und entfernt alle Kopien dieses Zeichen das Ende der `CStringT` Zeichenfolgendaten. Es beginnt am Ende der Zeichenfolge und funktioniert nach vorn. Wird beendet, wenn ein anderes Zeichen gefunden wird oder wenn `CSTringT` nicht mehr genügend Zeichendaten.  
  
 Die `CStringT& TrimRight(PCXSTR pszTargets)` Version akzeptiert eine auf Null endende Zeichenfolge, die alle anderen Zeichen für die Suche enthält. Entfernt alle Kopien dieser Zeichen in der `CStringT` Objekt. Am Ende der Zeichenfolge beginnt und funktioniert nach vorn. Wird beendet, wenn ein Zeichen gefunden wird, die nicht in der Zielzeichenfolge enthalten ist, oder wenn `CStringT` nicht mehr genügend Zeichendaten. Es wird nicht versucht, eine Teilzeichenfolge am Ende der gesamten Zielzeichenfolge entspricht `CStringT`.  
  
 Die `CStringT& TrimRight()` Version erfordert keine Parameter. Es entfernt alle nachgestellten Leerzeichen am Ende der `CStringT` Zeichenfolge. Leerzeichen können Zeilenumbrüche, Leerzeichen oder Tabstopps sein.  
  
-  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#138;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL/MFC-freigegeben Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)   
 [CSimpleStringT-Klasse](../../atl-mfc-shared/reference/csimplestringt-class.md)



