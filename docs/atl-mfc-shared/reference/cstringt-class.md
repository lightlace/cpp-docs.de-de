---
title: CStringT-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 253282092bb71b6d4a5c520355ab4f8b51015c9f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445138"
---
# <a name="cstringt-class"></a>CStringT-Klasse

Diese Klasse stellt eine `CStringT` Objekt.

## <a name="syntax"></a>Syntax

```

template<typename BaseType, class StringTraits>  
class CStringT :   
public CSimpleStringT<BaseType,
                      _CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>
                      ::c_bIsMFCDLLTraits>

```

#### <a name="parameters"></a>Parameter

*BaseType*  
Der Zeichentyp der String-Klasse. Einer der folgenden Werte ist möglich:

- **Char** (für ANSI-Zeichenfolgen).

- **"wchar_t"** (für Unicode-Zeichenfolgen).

- TCHAR (nach ANSI- und Unicode-Zeichenfolgen).

*StringTraits*  
Bestimmt, ob die Zeichenfolgenklasse benötigt Unterstützung für C-Laufzeit (CRT)-Klassenbibliotheken und, wo die Zeichenfolgenressourcen gespeichert sind. Einer der folgenden Werte ist möglich:

- **StrTraitATL < Wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsCRT < Wchar_t** &#124; `char` &#124; **TCHAR >>**

   Die Klasse erfordert, CRT-Unterstützung und sucht nach Ressourcenzeichenfolgen im Modul gemäß `m_hInstResource` (ein Mitglied der Anwendung Module-Klasse).

- **StrTraitATL < Wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsOS < Wchar_t** &#124; `char` &#124; **TCHAR >>**

   Die Klasse erfordert keine CRT-Unterstützung und sucht nach Ressourcenzeichenfolgen im Modul gemäß `m_hInstResource` (ein Mitglied der Anwendung Module-Klasse).

- **StrTraitMFC < Wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsCRT < Wchar_t** &#124; `char` &#124; **TCHAR >>**

   Die Klasse erfordert CRT-Unterstützung und sucht mithilfe der standardmäßigen MFC Suchalgorithmus Ressourcenzeichenfolgen.

- **StrTraitMFC < Wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsOS < Wchar_t** &#124; `char` &#124; **TCHAR >>**

   Die Klasse ist keine CRT-Unterstützung und sucht nach Ressourcenzeichenfolgen, die mithilfe der standardmäßigen MFC Suchalgorithmus erforderlich.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CStringT::CStringT](#cstringt)|Erstellt eine `CStringT` Objekts auf verschiedene Weise.|
|[CStringT:: ~ CStringT](#_dtorcstringt)|Zerstört ein `CStringT`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CStringT::AllocSysString](#allocsysstring)|Reserviert einen BSTR aus `CStringT` Daten.|
|[CStringT::AnsiToOem](#ansitooem)|Stellt eine direkte Konvertierung von ANSI-Zeichensatz in den OEM-Zeichensatz.|
|[CStringT::AppendFormat](#appendformat)|Fügt der formatierte Daten einer vorhandenen `CStringT` Objekt.|
|[CStringT::Collate](#collate)|Vergleicht zwei Zeichenfolgen (Groß-/Kleinschreibung unterschieden, die Gebietsschema-spezifische Verwendungsinformationen).|
|[CStringT::CollateNoCase](#collatenocase)|Vergleicht zwei Zeichenfolgen (Groß-/Kleinschreibung, verwendet gebietsschemaspezifischen Informationen).|
|[CStringT::Compare](#compare)|Vergleicht zwei Zeichenfolgen (Groß-/ Kleinschreibung).|
|[CStringT::CompareNoCase](#comparenocase)|Vergleicht zwei Zeichenfolgen (Groß-/Kleinschreibung).|
|[CStringT::Delete](#delete)|Löscht ein oder mehrere Zeichen aus einer Zeichenfolge an.|
|[CStringT::Find](#find)|Sucht nach einem Zeichen oder eine Teilzeichenfolge innerhalb einer größeren Zeichenfolge.|
|[CStringT::FindOneOf](#findoneof)|Sucht das erste übereinstimmende Zeichen aus einem Satz an.|
|[CStringT::Format](#format)|Formatiert die Zeichenfolge als `sprintf` ist.|
|[CStringT::FormatMessage](#formatmessage)|Formatiert eine Meldungszeichenfolge an.|
|[CStringT::FormatMessageV](#formatmessagev)|Formatiert eine Meldungszeichenfolge, die eine Variable Argumentliste verwenden.|
|[CStringT::FormatV](#formatv)|Formatiert die Zeichenfolge, die über eine Variable Liste von Argumenten.|
|[CStringT::GetEnvironmentVariable](#getenvironmentvariable)|Legt die Zeichenfolge auf den Wert der angegebenen Umgebungsvariablen fest.|
|[CStringT::Insert](#insert)|Fügt ein einzelnes Zeichen oder eine Teilzeichenfolge am angegebenen Index in der Zeichenfolge an.|
|[CStringT::Left](#left)|Extrahiert den linken Teil einer Zeichenfolge.|
|[CStringT::LoadString](#loadstring)|Lädt eine vorhandene `CStringT` Objekt aus einer Windows-Ressource.|
|[CStringT::MakeLower](#makelower)|Alle Zeichen in dieser Zeichenfolge in Kleinbuchstaben konvertiert.|
|[CStringT::MakeReverse](#makereverse)|Kehrt die Zeichenfolge an.|
|[CStringT::MakeUpper](#makeupper)|Alle Zeichen in dieser Zeichenfolge in Großbuchstaben konvertiert.|
|[CStringT::Mid](#mid)|Extrahiert den mittleren Teil einer Zeichenfolge.|
|[CStringT::OemToAnsi](#oemtoansi)|Stellt eine direkte Konvertierung aus dem OEM-Zeichensatz in den ANSI-Zeichensatz.|
|[CStringT::Remove](#remove)|Entfernt angegebene Zeichen aus einer Zeichenfolge.|
|[CStringT::Replace](#replace)|Ersetzt angegebene Zeichen mit anderen Zeichen.|
|[CStringT::ReverseFind](#reversefind)|Sucht ein Zeichen in einer größeren Zeichenfolge. beginnt am Ende.|
|[CStringT::Right](#right)|Extrahiert den rechten Teil einer Zeichenfolge.|
|[CStringT::SetSysString](#setsysstring)|Legt ein vorhandenes BSTR-Objekt mit Daten aus einer `CStringT` Objekt.|
|[CStringT::SpanExcluding](#spanexcluding)|Extrahiert Zeichen aus der Zeichenfolge, beginnend mit dem ersten Zeichen, die nicht in den Satz von Zeichen, die identifizierte `pszCharSet`.|
|[CStringT::SpanIncluding](#spanincluding)|Extrahiert eine Teilzeichenfolge, die nur die Zeichen in einer Menge enthält.|
|[CStringT::Tokenize](#tokenize)|Extrahiert werden Token in einer Zielzeichenfolge angegeben.|
|[CStringT::Trim](#trim)|Entfernt alle führenden und nachgestellten Leerraumzeichen aus der Zeichenfolge.|
|[CStringT::TrimLeft](#trimleft)|Entfernt führende Leerzeichen aus der Zeichenfolge.|
|[CStringT::TrimRight](#trimright)|Entfernt nachfolgende Leerzeichen aus der Zeichenfolge.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator =](#operator_eq)|Weist einen neuen Wert ein `CStringT` Objekt.|
|[CStringT::operator +](#operator_add)|Verkettet zwei Zeichenfolgen oder ein Zeichen und eine Zeichenfolge.|
|[CStringT::operator +=](#operator_add_eq)|Verkettet eine neue Zeichenfolge am Ende einer vorhandenen Zeichenfolge.|
|[CStringT::operator ==](#operator_eq_eq)|Bestimmt, ob zwei Zeichenfolgen logisch gleich sind.|
|[CStringT::operator! =](#operator_neq)|Bestimmt, ob zwei Zeichenfolgen logisch nicht gleich sind.|
|[CStringT::operator &lt;](#operator_lt)|Bestimmt, ob die Zeichenfolge auf der linken Seite des Operators kleiner als die Zeichenfolge auf der rechten Seite.|
|[CStringT::operator &gt;](#operator_gt)|Bestimmt, ob die Zeichenfolge links vom Operator größer als die Zeichenfolge auf der rechten Seite ist.|
|[CStringT::operator &lt;=](#operator_lt_eq)|Bestimmt, ob die Zeichenfolge links vom Operator kleiner als oder gleich der Zeichenfolge auf der rechten Seite ist.|
|[CStringT::operator &gt;=](#operator_gt_eq)|Bestimmt, ob die Zeichenfolge links vom Operator größer als oder gleich der Zeichenfolge auf der rechten Seite ist.|

## <a name="remarks"></a>Hinweise

`CStringT` erbt von [CSimpleStringT-Klasse](../../atl-mfc-shared/reference/csimplestringt-class.md). Erweiterte Funktionen, z. B. Zeichen Manipulation, Sortierung und Suche werden von implementiert `CStringT`.

> [!NOTE]
> `CStringT` Objekte sind Ausnahmen auslösen kann. Dies tritt auf, wenn eine `CStringT` Objekt aus irgendeinem Grund nicht genügend Arbeitsspeicher ausgeführt wird.

Ein `CStringT` Objekt besteht aus einer Zeichenfolge variabler Länge. `CStringT` bietet Funktionen und Operatoren, die mithilfe der Syntax, die von Basic ähnelt. Verkettung und Vergleichsoperatoren, zusammen mit vereinfachte Speicherverwaltung, stellen `CStringT` Objekte, die einfacher zu verwenden als normales Zeichen-Arrays.

> [!NOTE]
>  Obwohl es möglich ist, erstellen Sie `CStringT` Instanzen, die enthalten eingebettete Null-Zeichen, wir Raten sie. Aufrufen von Methoden und Operatoren für `CStringT` Objekte, die eingebettete Null-Zeichen enthalten können zu unbeabsichtigten Ergebnissen führen.

Mit anderen Kombinationen von der `BaseType` und `StringTraits` Parameter `CStringT` Objekte kann stammen in der folgenden Typen, die vordefiniert wurden, die von den ATL-Bibliotheken.

Wenn in ATL-Anwendungen zu verwenden:

`CString`, `CStringA`, und `CStringW` exportiert werden, von der MFC-DLL (MFC90. DLL), jedoch niemals auf Benutzer DLLs. Dies geschieht, um zu verhindern, dass `CStringT` aus wird mehrfach definiert.

> [!NOTE]
>  Wenn Ihr Code die problemumgehung für Linkerfehler, die enthält in beschriebenen [Linking Errors When You Import CString-Derived Klassen "(Q309801)](https://support.microsoft.com/help/309801/you-may-receive-an-lnk2019-error-message-when-you-build-a-visual-c-200), sollten Sie diesen Code entfernen. Es ist nicht mehr erforderlich.

Die folgenden Zeichenfolgen-Datentypen sind in MFC-basierten Anwendungen verfügbar:

|CStringT-Typ|Deklaration|
|-------------------|-----------------|
|`CStringA`|ANSI-Zeichen geben die Zeichenfolge mit der CRT-Unterstützung.|
|`CStringW`|Geben Sie ein Unicode-Zeichen-Zeichenfolge mit der CRT-Unterstützung.|
|`CString`|ANSI- und Unicode-Zeichen-Typen mit der CRT-Unterstützung.|

Die folgenden Zeichenfolgen-Datentypen sind in-Projekten verfügbar, in dem ATL_CSTRING_NO_CRT definiert ist:

|CStringT-Typ|Deklaration|
|-------------------|-----------------|
|`CAtlStringA`|ANSI-Zeichen-Zeichenfolgentyp ohne CRT-Support.|
|`CAtlStringW`|Ein Unicode-Zeichen-Zeichenfolgentyp ohne CRT-Support.|
|`CAtlString`|ANSI- und Unicode-Zeichen-Typen ohne CRT-Support.|

Die folgenden Zeichenfolgen-Datentypen sind in-Projekten verfügbar, in der ATL_CSTRING_NO_CRT nicht definiert ist:

|CStringT-Typ|Deklaration|
|-------------------|-----------------|
|`CAtlStringA`|ANSI-Zeichen geben die Zeichenfolge mit der CRT-Unterstützung.|
|`CAtlStringW`|Geben Sie ein Unicode-Zeichen-Zeichenfolge mit der CRT-Unterstützung.|
|`CAtlString`|ANSI- und Unicode-Zeichen-Typen mit der CRT-Unterstützung.|

`CString` Objekte haben auch die folgenden Merkmale auf:

- `CStringT` Objekte, die als Ergebnis der Verkettungsvorgänge anwachsen können.

- `CStringT` Führen Sie die Objekte "Wert-Semantik." Denken Sie an einer `CStringT` Objekt als eine tatsächliche Zeichenfolge und nicht als ein Zeiger auf eine Zeichenfolge.

- Sie können frei ersetzen `CStringT` von Objekten für die `PCXSTR` Funktionsargumente.

- Benutzerdefinierte Speicherverwaltung für Zeichenfolgenpuffer. Weitere Informationen finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="cstringt-predefined-types"></a>CStringT vordefinierte Typen

Da `CStringT` verwendet eine Template-Argument, um den Zeichentyp zu definieren (entweder ["wchar_t"](../../c-runtime-library/standard-types.md) oder [Char](../../c-runtime-library/standard-types.md)) unterstützt, Webmethoden-Parametertypen können kompliziert sein manchmal. Um dieses Problem zu vereinfachen, eine Reihe von vordefinierten Typen definiert und verwendet die `CStringT` Klasse. Die folgende Tabelle enthält die verschiedenen Typen:

|name|Beschreibung|
|----------|-----------------|
|`XCHAR`|Ein einzelnes Zeichen (entweder **"wchar_t"** oder **Char**) mit dem gleichen Zeichen wie die `CStringT` Objekt.|
|`YCHAR`|Ein einzelnes Zeichen (entweder **"wchar_t"** oder **Char**) mit den entgegengesetzten Zeichentyp als die `CStringT` Objekt.|
|`PXSTR`|Ein Zeiger auf eine Zeichenfolge (entweder **"wchar_t"** oder **Char**) mit dem gleichen Zeichen wie die `CStringT` Objekt.|
|`PYSTR`|Ein Zeiger auf eine Zeichenfolge (entweder **"wchar_t"** oder **Char**) mit den entgegengesetzten Zeichentyp als die `CStringT` Objekt.|
|`PCXSTR`|Ein Zeiger auf eine **const** Zeichenfolge (entweder **"wchar_t"** oder **Char**) mit dem gleichen Zeichen wie die `CStringT` Objekt.|
|`PCYSTR`|Ein Zeiger auf eine **const** Zeichenfolge (entweder **"wchar_t"** oder **Char**) mit den entgegengesetzten Zeichentyp als die `CStringT` Objekt.|

> [!NOTE]
>  Code, der zuvor nicht dokumentierte Methoden verwendet `CString` (z. B. `AssignCopy`) ersetzt werden muss, mit Code, die folgenden dokumentierten Methoden der verwendet `CStringT` (z. B. `GetBuffer` oder `ReleaseBuffer`). Diese Methoden werden von geerbt `CSimpleStringT`.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)

`CStringT`

## <a name="requirements"></a>Anforderungen

|Header|Verwenden Sie für|
|------------|-------------|
|CStringT.h|Nur MFC-String-Objekte|
|atlstr.h|MFC-fremde String-Objekte|

##  <a name="allocsysstring"></a>  CStringT::AllocSysString

Ordnet eine Automation-kompatible Zeichenfolge des Typs BSTR und kopiert den Inhalt der `CStringT` Objekt ein, einschließlich des abschließenden Null-Zeichens.

```
BSTR AllocSysString() const;  
```

### <a name="return-value"></a>Rückgabewert

Die neu zugeordnete Zeichenfolge.

### <a name="remarks"></a>Hinweise

In MFC-Programmen eine [CMemoryException-Klasse](../../mfc/reference/cmemoryexception-class.md) wird ausgelöst, wenn nicht genügend Arbeitsspeicher vorhanden ist. ATL-Programme eine [CAtlException](../../atl/reference/catlexception-class.md) ausgelöst. Diese Funktion wird normalerweise verwendet, um die Zeichenfolgen für die Automatisierung zurückzugeben.

Häufig, wenn diese Zeichenfolge an eine COM-Funktion übergeben wird als [in] Parameter, wird dadurch muss der Aufrufer die Zeichenfolge frei. Dies kann erfolgen mithilfe von [SysFreeString](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-sysfreestring), wie im Windows SDK beschrieben. Weitere Informationen finden Sie unter [zuweisen und Freigeben von Arbeitsspeicher für einen BSTR](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md).

Weitere Informationen zu OLE-Allocation-Funktionen in Windows finden Sie unter [SysAllocString](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-sysallocstring) im Windows SDK.  


### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CStringT::AllocSysString`.

[!code-cpp[NVC_ATLMFC_Utilities#105](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]

##  <a name="ansitooem"></a>  CStringT::AnsiToOem

Konvertiert alle Zeichen in dieser `CStringT` Objekt aus dem ANSI-Zeichensatz in den OEM-Zeichensatz.

```
void AnsiToOem();
```

### <a name="remarks"></a>Hinweise

Die Funktion ist nicht verfügbar, wenn _UNICODE definiert ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#106](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]

##  <a name="appendformat"></a>  CStringT::AppendFormat

Fügt der formatierte Daten einer vorhandenen `CStringT` Objekt.

```
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```

### <a name="parameters"></a>Parameter

*pszFormat*  
Eine Zeichenfolge Steuerelement formatieren.

*nFormatID*  
Der Ressourcenbezeichner für die Zeichenfolge, die die Format-Zeichenfolge enthält.

*Argument*  
Optionale Argumente.

### <a name="remarks"></a>Hinweise

Diese Funktion formatiert und fügt eine Abfolge von Zeichen und Werten in der `CStringT`. Jedes optionales Argument (sofern vorhanden) konvertiert und gemäß der jeweiligen Formatangabe in angefügt *PszFormat* oder über die Zeichenfolgenressource identifizierte *nFormatID*.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#107](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]

##  <a name="collate"></a>  CStringT::Collate

Vergleicht zwei Zeichenfolgen mithilfe der Funktion für generischen Text `_tcscoll`.

```
int Collate(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Parameter

*psz*  
Die andere Zeichenfolge für den Vergleich verwendet.

### <a name="return-value"></a>Rückgabewert

0 (null), wenn die Zeichenfolgen identisch sind, < 0, wenn diese `CStringT` Objekt ist kleiner als *Psz*, oder > 0, wenn diese `CStringT` -Quellobjekt ist größer als *Psz*.

### <a name="remarks"></a>Hinweise

Die Funktion für generischen Text `_tcscoll`, die in TCHAR definiert ist. H, ordnet entweder `strcoll`, `wcscoll`, oder `_mbscoll`, abhängig von den Zeichensatz an, die zum Zeitpunkt der Kompilierung definiert ist. Jede Funktion führt einen Vergleich der Zeichenfolgen gemäß der Codepage, die Groß-/Kleinschreibung momentan verwendet. Weitere Informationen finden Sie unter [Strcoll, Wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).

##  <a name="collatenocase"></a>  CStringT::CollateNoCase

Vergleicht zwei Zeichenfolgen mithilfe der Funktion für generischen Text `_tcscoll`.

```
int CollateNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Parameter

*psz*  
Die andere Zeichenfolge für den Vergleich verwendet.

### <a name="return-value"></a>Rückgabewert

NULL, wenn die Zeichenfolgen sind identisch (Groß-/Kleinschreibung), < 0, wenn diese `CStringT` Objekt ist kleiner als *Psz* (Ignorieren der Groß-/Kleinschreibung), oder > 0, wenn diese `CStringT` -Quellobjekt ist größer als *Psz* (Ignorieren der Groß-/Kleinschreibung).

### <a name="remarks"></a>Hinweise

Die Funktion für generischen Text `_tcscoll`, die in TCHAR definiert ist. H, ordnet entweder `stricoll`, `wcsicoll`, oder `_mbsicoll`, abhängig von den Zeichensatz an, die zum Zeitpunkt der Kompilierung definiert ist. Jede Funktion führt einen Vergleich der Zeichenfolgen, Groß-/Kleinschreibung entsprechend der derzeit verwendeten Codepage. Weitere Informationen finden Sie unter [Strcoll, Wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#109](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]

##  <a name="compare"></a>  CStringT::Compare

Vergleicht zwei Zeichenfolgen (Groß-/ Kleinschreibung).

```
int Compare(PCXSTR psz) const; 
```

### <a name="parameters"></a>Parameter

*psz*  
Die andere Zeichenfolge für den Vergleich verwendet.

### <a name="return-value"></a>Rückgabewert

0 (null), wenn die Zeichenfolgen identisch sind, < 0, wenn diese `CStringT` Objekt ist kleiner als *Psz*, oder > 0, wenn diese `CStringT` -Quellobjekt ist größer als *Psz*.

### <a name="remarks"></a>Hinweise

Die Funktion für generischen Text `_tcscmp`, die in TCHAR definiert ist. H, ordnet entweder `strcmp`, `wcscmp`, oder `_mbscmp`, abhängig von den Zeichensatz an, die zum Zeitpunkt der Kompilierung definiert ist. Jede Funktion führt einen Vergleich der Zeichenfolgen, die Groß-/Kleinschreibung und ist nicht vom Gebietsschema beeinflusst. Weitere Informationen finden Sie unter [Strcmp, Wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md).

Wenn die Zeichenfolge eingebettete NULL-Werte enthält, wird für Vergleichszwecke die Zeichenfolge als bei der ersten eingebettete Null-Zeichen abgeschnitten.

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `CStringT::Compare`.

[!code-cpp[NVC_ATLMFC_Utilities#110](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]

##  <a name="comparenocase"></a>  CStringT::CompareNoCase

Vergleicht zwei Zeichenfolgen (Groß-/Kleinschreibung).

```
int CompareNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>Parameter

*psz*  
Die andere Zeichenfolge für den Vergleich verwendet.

### <a name="return-value"></a>Rückgabewert

NULL, wenn die Zeichenfolgen identisch sind (Ignorieren der Groß-/Kleinschreibung), < 0, wenn diese `CStringT` Objekt ist kleiner als *Psz* (Ignorieren der Groß-/Kleinschreibung), oder > 0, wenn diese `CStringT` -Quellobjekt ist größer als *Psz* (Ignorieren der Groß-/Kleinschreibung).

### <a name="remarks"></a>Hinweise

Die Funktion für generischen Text `_tcsicmp`, die in TCHAR definiert ist. H, ordnet entweder `_stricmp`, `_wcsicmp` oder `_mbsicmp`, abhängig von den Zeichensatz an, die zum Zeitpunkt der Kompilierung definiert ist. Jede Funktion führt einen Vergleich Groß-/Kleinschreibung der Zeichenfolgen. Der Vergleich, hängt von den LC_CTYPE-Aspekt des dem Gebietsschema aber nicht LC_COLLATE ab. Weitere Informationen finden Sie unter [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md).

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

*PCH*  
Ein Zeiger auf ein Array von Zeichen Länge *nLength*, enden nicht auf Null.

*nLength*  
Die Anzahl der Zeichen im *Pch*.

*ch*  
Ein einzelnes Zeichen.

*pszSrc*  
Eine mit Null endende Zeichenfolge, die in diese kopiert werden `CStringT` Objekt.

*pStringMgr*  
Ein Zeiger auf die Speicher-Manager für die `CStringT` Objekt. Weitere Informationen zu `IAtlStringMgr` und Speicherverwaltung für `CStringT`, finden Sie unter [Speicherverwaltung mit CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

*strSrc*  
Eine vorhandene `CStringT` Objekt, das in diese kopiert werden `CStringT` Objekt. Weitere Informationen zu `CThisString` und `CThisSimpleString`, finden Sie im Abschnitt "Hinweise".

*varSrc*  
Variant-Objekts, das in diese kopiert werden `CStringT` Objekt.

*BaseType*  
Der Zeichentyp der String-Klasse. Einer der folgenden Werte ist möglich:

**Char** (für ANSI-Zeichenfolgen).

**"wchar_t"** (für Unicode-Zeichenfolgen).

TCHAR (nach ANSI- und Unicode-Zeichenfolgen).

*bMFCDLL*  
Boolescher Wert, der angibt, ob das Projekt eine MFC-DLL (TRUE) oder nicht ist (FALSE).

*SystemString*  
Muss `System::String`, und das Projekt muss mit "/ CLR" kompiliert werden.

*pString*  
Ein Handle für ein `CStringT` Objekt.

### <a name="remarks"></a>Hinweise

Da die Konstruktoren der Eingabedaten in den neuen zugeordneten Speicher kopieren, sollten Sie bedenken, dass der Speicher Ausnahmen führen können. Beachten Sie, dass einige dieser Konstruktoren als Funktionen für die typkonvertierung fungieren. Dadurch können Sie z. B. eine LPTSTR ersetzen, in denen eine `CStringT` Objekt wird erwartet.

- `CStringT`( `LPCSTR` `lpsz` ): Erstellt eine Unicode `CStringT` aus einer ANSI-Zeichenfolge. Sie können diesen Konstruktor auch verwenden, beim Laden einer Zeichenfolgenressource wie im folgenden Beispiel gezeigt.

- `CStringT(` `LPCWSTR` `lpsz` ): Erstellt eine `CStringT` aus einer Unicodezeichenfolge.

- `CStringT`( `const unsigned char*` `psz` ): Ermöglicht das Erstellen einer `CStringT` von einem Zeiger auf **unsigned Char**.

> [!NOTE]
>  Definieren Sie das Makro _CSTRING_DISABLE_NARROW_WIDE_CONVERSION implizite zeichenfolgenkonvertierung zwischen ANSI- und Unicode-Zeichenfolgen zu deaktivieren. Das Makro schließt von Kompilierung-Konstruktoren, die Unterstützung der Konvertierung.

Beachten Sie, dass die *StrSrc* Parameter kann es sich um eine `CStringT` oder `CThisSimpleString` Objekt. Für `CStringT`, gehen Sie den Standard-Instanziierungen (`CString`, `CStringA`, oder `CStringW`); `CThisSimpleString`, verwenden Sie eine **dies** Zeiger. `CThisSimpleString` deklariert eine Instanz der [CSimpleStringT-Klasse](../../atl-mfc-shared/reference/csimplestringt-class.md), d.h. eine kleinere-Klasse mit weniger integrierter Funktionen als die `CStringT` Klasse.

Die Überladungsoperator `CSimpleStringT<>&()` erstellt eine `CStringT` -Objekt aus einem `CSimpleStringT` Deklaration.

> [!NOTE]
>  Obwohl es möglich ist, erstellen Sie `CStringT` Instanzen, die enthalten eingebettete Null-Zeichen, wir Raten sie. Aufrufen von Methoden und Operatoren für `CStringT` Objekte, die eingebettete Null-Zeichen enthalten können zu unbeabsichtigten Ergebnissen führen.

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

Löscht ein oder mehrere Zeichen aus einer Zeichenfolge, beginnend mit dem Zeichen am angegebenen Index an.

```
int Delete(int iIndex, int nCount = 1);
```

### <a name="parameters"></a>Parameter

*iIndex*  
Der nullbasierte Index des ersten Zeichens in der `CStringT` zu löschenden Objekts.

*nCount*  
Die Anzahl der zu entfernenden Zeichen.

### <a name="return-value"></a>Rückgabewert

Die Länge der Zeichenfolge geändert.

### <a name="remarks"></a>Hinweise

Wenn *nCount* ist länger als die Zeichenfolge, die den Rest der Zeichenfolge entfernt werden.

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

*pszSub*  
Eine zu suchende Teilzeichenfolge.

*iStart*  
Der Index des Zeichens in die Zeichenfolge, die mit der Suche zu starten, oder 0, um von vorn zu beginnen.

*ch*  
Einem einzelnen Zeichen, die gesucht werden soll.

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index des ersten Zeichens in dieser `CStringT` -Objekt, das der angeforderten Teilzeichenfolge oder Zeichen entspricht; 1, wenn das Zeichen oder eine Teilzeichenfolge nicht gefunden wird.

### <a name="remarks"></a>Hinweise

Die Funktion wird überladen, um sowohl einzelnen Zeichen akzeptieren (vergleichbar mit der Run-Time-Funktion `strchr`) und Zeichenfolgen (ähnlich wie `strstr`).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#114](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]

##  <a name="findoneof"></a>  CStringT::FindOneOf

Diese Zeichenfolge nach dem ersten Zeichen, die Übereinstimmung mit jedem Zeichen, die in enthaltenen sucht *PszCharSet*.

```
int FindOneOf(PCXSTR pszCharSet) const throw();
```

### <a name="parameters"></a>Parameter

*pszCharSet*  
Zeichenfolge mit Zeichen für den Abgleich.

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index des ersten Zeichens in dieser Zeichenfolge, die auch in *PszCharSet*; 1, wenn keine Übereinstimmung vorhanden ist.

### <a name="remarks"></a>Hinweise

Sucht das erste Vorkommen eines beliebigen Zeichen *PszCharSet*.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#115](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]

##  <a name="format"></a>  CStringT::Format

Schreibt formatierte Daten in einem `CStringT` in der gleichen Weise wie [Sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) Datenformate in einem C-Stil-Zeichenarray.

```
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```

### <a name="parameters"></a>Parameter

*nFormatID*  
Der Ressourcenbezeichner für die Zeichenfolge, die die Format-Zeichenfolge enthält.

*pszFormat*  
Eine Zeichenfolge Steuerelement formatieren.

*Argument*  
Optionale Argumente.

### <a name="remarks"></a>Hinweise

Diese Funktion formatiert und speichert eine Reihe von Zeichen und Werte in der `CStringT`. Jedes optionales Argument (sofern vorhanden) konvertiert und ausgegeben wird, entsprechend der jeweiligen Formatangabe in *PszFormat* oder über die Zeichenfolgenressource identifizierte *nFormatID*.

Der Aufruf schlägt fehl, wenn das String-Objekt selbst als Parameter an angeboten wird `Format`. Der folgende Code wird z. B. zu unvorhersehbaren Ergebnissen führen:

[!code-cpp[NVC_ATLMFC_Utilities#116](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]

Weitere Informationen finden Sie unter [Format Specification Syntax: printf and wprintf Functions (Syntax der Formatangabe: printf- und wprintf-Funktionen)](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#117](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]

##  <a name="formatmessage"></a>  CStringT::FormatMessage

Formatiert eine Meldungszeichenfolge an.

```
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```

### <a name="parameters"></a>Parameter

*nFormatID*  
Der Ressourcenbezeichner für die Zeichenfolge, die den Nachrichtentext nicht formatierte enthält.

*pszFormat*  
Verweist auf die formatsteuerzeichenfolge. Für einfügungen überprüft wird und entsprechend formatiert. Die Formatzeichenfolge wird-Laufzeitfunktion ähnelt *Printf*-Formatzeichenfolgen formatieren, mit der Ausnahme für die Parameter in beliebiger Reihenfolge eingefügt werden können.

*Argument*  
Optionale Argumente.

### <a name="remarks"></a>Hinweise

Die Funktion erfordert als Eingabe eine Nachrichtendefinition. Der Nachrichtendefinition richtet sich nach *PszFormat* oder über die Zeichenfolgenressource identifizierte *nFormatID*. Kopiert die formatierte Nachrichtentext für die Funktion der `CStringT` Objekt eingebettet verarbeitet einfügen Sequenzen aus, wenn angefordert.

> [!NOTE]
> `FormatMessage` versucht, den Systemspeicher für das neu formatierte Zeichenfolge zu reservieren. Wenn dieser Versuch fehlschlägt, wird automatisch eine Memory-Ausnahme ausgelöst.

Jeder Einfügung benötigen eine entsprechende Parameter folgt der *PszFormat* oder *nFormatID* Parameter. In den Meldungstext werden mehrere Escapesequenzen für die dynamische Formatierung der Nachricht unterstützt. Weitere Informationen finden Sie in der Windows [FormatMessage](/windows/desktop/api/winbase/nf-winbase-formatmessage) -Funktion in das Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#118](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]

##  <a name="formatmessagev"></a>  CStringT::FormatMessageV

Formatiert eine Meldungszeichenfolge, die eine Variable Argumentliste verwenden.

```
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```

### <a name="parameters"></a>Parameter

*pszFormat*  
Verweist auf die formatsteuerzeichenfolge. Für einfügungen überprüft wird und entsprechend formatiert. Die Formatzeichenfolge wird-Laufzeitfunktion ähnelt `printf`-Formatzeichenfolgen formatieren, mit der Ausnahme für die Parameter in beliebiger Reihenfolge eingefügt werden können.

*pArgList*  
Zeiger auf eine Liste von Argumenten.

### <a name="remarks"></a>Hinweise

Die Funktion erfordert als Eingabe eine Nachrichtendefinition von bestimmt *PszFormat*. Kopiert die Funktion den formatierten Text und eine Variable Liste von Argumenten, die die `CStringT` Objekt eingebettet verarbeitet einfügen Sequenzen aus, wenn angefordert.

> [!NOTE]
> `FormatMessageV` Aufrufe [CStringT::FormatMessage](#formatmessage), die versucht, den Systemspeicher für die neu formatierte Zeichenfolge zuweisen. Wenn dieser Versuch fehlschlägt, wird automatisch eine Memory-Ausnahme ausgelöst.

Weitere Informationen finden Sie in der Windows [FormatMessage](/windows/desktop/api/winbase/nf-winbase-formatmessage) -Funktion in das Windows SDK.

##  <a name="formatv"></a>  CStringT::FormatV

Formatiert eine Meldungszeichenfolge, die eine Variable Argumentliste verwenden.

```
void FormatV(PCXSTR pszFormat, va_list args);
```

### <a name="parameters"></a>Parameter

*pszFormat*  
Verweist auf die formatsteuerzeichenfolge. Für einfügungen überprüft wird und entsprechend formatiert. Die Formatzeichenfolge wird-Laufzeitfunktion ähnelt `printf`-Formatzeichenfolgen formatieren, mit der Ausnahme für die Parameter in beliebiger Reihenfolge eingefügt werden können.

*args*  
Zeiger auf eine Liste von Argumenten.

### <a name="remarks"></a>Hinweise

Schreibt eine formatierte Zeichenfolge und eine Variable Liste von Argumenten, die eine `CStringT` Zeichenfolge in der gleichen Weise wie `vsprintf_s` Datenformate in einem C-Stil-Zeichenarray.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#119](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#120](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]

##  <a name="getenvironmentvariable"></a>  CStringT::GetEnvironmentVariable

Legt die Zeichenfolge auf den Wert der angegebenen Umgebungsvariablen fest.

```
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```

### <a name="parameters"></a>Parameter

*pszVar*  
Zeiger auf eine auf Null endende Zeichenfolge, die die Umgebungsvariable angibt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Ruft den Wert der angegebenen Variablen in dem Umgebungsblock des aufrufenden Prozesses ab. Der Wert ist in Form einer Null-terminierte Zeichenfolge von Zeichen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#121](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]

##  <a name="insert"></a>  CStringT::Insert

Fügt ein einzelnes Zeichen oder eine Teilzeichenfolge am angegebenen Index in der Zeichenfolge an.

```
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```

### <a name="parameters"></a>Parameter

*iIndex*  
Der Index des Zeichens, vor denen der Einfügevorgang stattfinden soll.

*psz*  
Ein Zeiger auf die einzufügende Teilzeichenfolge.

*ch*  
Das Zeichen eingefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Die Länge der Zeichenfolge geändert.

### <a name="remarks"></a>Hinweise

Die *iIndex* Parameter identifiziert die erste Zeichen, das verschoben wird, um Platz für das Zeichen oder eine Teilzeichenfolge bereitzustellen. Wenn *nIndex* ist 0 (null), bevor Sie die gesamte Zeichenfolge ist das Einfügen erfolgt. Wenn *nIndex* ist größer als die Länge der Zeichenfolge, die Funktion die vorhandene Zeichenfolge zu verketten wird und des neuen Materials bereitgestellt wird, indem Sie entweder die *ch* oder *Psz*.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#122](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]

##  <a name="left"></a>  CStringT::Left

Extrahiert die am weitesten links stehende *nCount* Zeichen aus diesem `CStringT` Objekt und gibt eine Kopie der extrahierten Teilzeichenfolge zurück.

```
CStringT Left(int nCount) const; 
```

### <a name="parameters"></a>Parameter

*nCount*  
Die Anzahl der aus diesem `CStringT`-Objekt zu extrahierenden Zeichen.

### <a name="return-value"></a>Rückgabewert

Ein `CStringT`-Objekt, das eine Kopie des angegebenen Zeichenbereichs enthält. Das zurückgegebene `CStringT`-Objekt ist ggf. leer.

### <a name="remarks"></a>Hinweise

Wenn *nCount* überschreitet die Länge der Zeichenfolge, und klicken Sie dann die gesamte Zeichenfolge extrahiert wird. `Left` ähnelt der `Left`-Funktion von ///Visual Basic.

Für Multi-Byte-Zeichensätzen (MBCS), *nCount* behandelt jede Sequenz von 8-Bit-als-Zeichen, sodass *nCount* gibt die Anzahl der Multibytezeichen 2 multipliziert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#123](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]

##  <a name="loadstring"></a>  CStringT::LoadString

Liest eine Zeichenfolgenressource Windows, das identifizierte *nID*, in einem vorhandenen `CStringT` Objekt.

```
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```

### <a name="parameters"></a>Parameter

*hInstance*  
Ein Handle für die Instanz des Moduls.

*nID*  
Eine Windows-Zeichenfolgen-Ressourcen-ID.

*wLanguageID*  
Die Sprache der Zeichenfolgenressource.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn Ressourcenlast erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Lädt die Zeichenfolgenressource (*nID*) aus dem angegebenen Modul (*hInstance*) unter Verwendung der angegebenen Sprache (*wLanguage*).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#124](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]

##  <a name="makelower"></a>  CStringT::MakeLower

Konvertiert die `CStringT` Objekt, das eine Zeichenfolge aus Kleinbuchstaben.

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

Die resultierende umgekehrt Zeichenfolge.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#126](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]

##  <a name="makeupper"></a>  CStringT::MakeUpper

Konvertiert die `CStringT` Objekt, das eine Zeichenfolge in Großbuchstaben.

```
CStringT& MakeUpper();
```

### <a name="return-value"></a>Rückgabewert

Die resultierende Zeichenfolge aus Großbuchstaben.

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#127](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]

##  <a name="mid"></a>  CStringT::Mid

Extrahiert eine Teilzeichenfolge der Länge *nCount* Zeichen aus diesem `CStringT` -Objekt, beginnend an Position *iFirst* (nullbasiert).

```
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const; 
```

### <a name="parameters"></a>Parameter

*iFirst*  
Der nullbasierte Index des ersten Zeichens in dieser `CStringT` -Objekt, das in die extrahierte Teilzeichenfolge enthalten sein soll.

*nCount*  
Die Anzahl der aus diesem `CStringT`-Objekt zu extrahierenden Zeichen. Wenn dieser Parameter nicht angegeben ist, wird der Rest der Zeichenfolge extrahiert.

### <a name="return-value"></a>Rückgabewert

Ein `CStringT`-Objekt, das eine Kopie des angegebenen Zeichenbereichs enthält. Beachten Sie, dass die zurückgegebene `CStringT` Objekt kann leer sein.

### <a name="remarks"></a>Hinweise

Die Funktion gibt eine Kopie der extrahierten Teilzeichenfolge zurück. `Mid` ähnelt der grundlegenden Mid-Funktion (außer, dass Indizes in Basic, 1-basiert sind).

Für multibyte-Zeichensätze (MBCS), setzt *nCount* bezieht sich auf jedes 8-Bit-Zeichen, d. h. ein und die nachfolgenden Byte in einem multibyte-Zeichen werden als zwei Zeichen gezählt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#128](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]

##  <a name="oemtoansi"></a>  CStringT::OemToAnsi

Konvertiert alle Zeichen in dieser `CStringT` Objekt aus dem OEM-Zeichensatz in den ANSI-Zeichensatz.

```
void OemToAnsi();
```

### <a name="remarks"></a>Hinweise

Diese Funktion ist nicht verfügbar, wenn _UNICODE definiert ist.

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

*Kapitel 1*  
Eine ANSI- oder Unicode-Zeichen mit einer Zeichenfolge verketten.

*Ch2*  
Eine ANSI- oder Unicode-Zeichen mit einer Zeichenfolge verketten.

*str1*  
Ein `CStringT` zum Verketten von mit einer Zeichenfolge oder ein Zeichen.

*str2*  
Ein `CStringT` zum Verketten von mit einer Zeichenfolge oder ein Zeichen.

*psz1*  
Ein Zeiger auf einen Null-terminierte Zeichenfolge mit einer Zeichenfolge oder ein Zeichen zu verketten.

*psz2*  
Ein Zeiger auf eine Zeichenfolge, die mit einer Zeichenfolge oder ein Zeichen zu verketten.

### <a name="remarks"></a>Hinweise

Es gibt sieben Arten von Überladung von der `CStringT::operator+` Funktion. Die erste Version verkettet zwei vorhandene `CStringT` Objekte. Die nächsten beiden Verketten einer `CStringT` Objekt und eine Null-terminierte Zeichenfolge. Die nächsten beiden Verketten einer `CStringT` -Objekt und ein ANSI-Zeichen. Die letzten zwei Verketten einer `CStringT` -Objekt und ein Unicode-Zeichen.

> [!NOTE]
>  Obwohl es möglich ist, erstellen Sie `CStringT` Instanzen, die enthalten eingebettete Null-Zeichen, wir Raten sie. Aufrufen von Methoden und Operatoren für `CStringT` Objekte, die eingebettete Null-Zeichen enthalten können zu unbeabsichtigten Ergebnissen führen.

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

*bMFCDLL*  
Ein boolescher Wert, der angibt, ob das Projekt eine MFC-DLL oder nicht ist.

*BaseType*  
Der Basistyp Zeichenfolge.

*var*  
Variant-Objekts, das mit dieser Zeichenfolge verkettet.

*ch*  
Eine ANSI- oder Unicode-Zeichen mit einer Zeichenfolge verketten.

*pszSrc*  
Ein Zeiger auf die ursprüngliche Zeichenfolge verkettet werden.

*strSrc*  
Ein `CStringT` dieser Zeichenfolge zu verketten.

### <a name="remarks"></a>Hinweise

Der Operator akzeptiert eine andere `CStringT` -Objekt, einen Zeichenzeiger oder ein einzelnes Zeichen. Sie sollten bedenken, dass der Speicher Ausnahmen können auftreten, wenn dieser Operator für zeichenfolgenverkettung verwenden, da mit neuer Speicher für diese hinzugefügten Zeichen zugewiesen werden kann `CStringT` Objekt.

Informationen zum `CThisSimpleString`, finden Sie im Abschnitt "Hinweise" [CStringT::CStringT](#cstringt).

> [!NOTE]
>  Obwohl es möglich ist, erstellen Sie `CStringT` Instanzen, die enthalten eingebettete Null-Zeichen, wir Raten sie. Aufrufen von Methoden und Operatoren für `CStringT` Objekte, die eingebettete Null-Zeichen enthalten können zu unbeabsichtigten Ergebnissen führen.

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

*Kapitel 1*  
Eine ANSI- oder Unicode-Zeichen für den Vergleich.

*Ch2*  
Eine ANSI- oder Unicode-Zeichen für den Vergleich.

*str1*  
Ein `CStringT` für den Vergleich.

*str2*  
Ein `CStringT` für den Vergleich.

*psz1*  
Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.

*psz2*  
Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.

### <a name="remarks"></a>Hinweise

Testet, ob eine Zeichenfolge oder die Zeichen auf der linken Seite entspricht einer Zeichenfolge oder ein Zeichen auf der rechten Seite, und "true" oder "false" entsprechend gibt an.

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

*Kapitel 1*  
Eine ANSI- oder Unicode-Zeichen mit einer Zeichenfolge verketten.

*Ch2*  
Eine ANSI- oder Unicode-Zeichen mit einer Zeichenfolge verketten.

*str1*  
Ein `CStringT` für den Vergleich.

*str2*  
Ein `CStringT` für den Vergleich.

*psz1*  
Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.

*psz2*  
Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.

### <a name="remarks"></a>Hinweise

Testet, ob eine Zeichenfolge oder die Zeichen auf der linken Seite ungleich in eine Zeichenfolge oder ein Zeichen in der rechten Seite ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#143](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]

##  <a name="operator_lt"></a>  CStringT::operator &lt;

Bestimmt, ob die Zeichenfolge links vom Operator kleiner als die Zeichenfolge auf der rechten Seite ist.

```
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parameter

*str1*  
Ein `CStringT` für den Vergleich.

*str2*  
Ein `CStringT` für den Vergleich.

*psz1*  
Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.

*psz2*  
Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.

### <a name="remarks"></a>Hinweise

Ein lexikografischer Vergleich zwischen Zeichenfolgen Zeichen für Zeichen bis:

- Er zwei korrespondierende ungleiche Zeichen findet, und deren Vergleich als Ergebnis des Vergleichs zweier Zeichenfolgen genommen wird.

- Er keine Ungleichheiten findet, aber eine Zeichenfolge mehr Zeichen hat als die andere und die kürzere Zeichenfolge als kleiner als die längere Zeichenfolge betrachtet wird.

- Er keine Ungleichheiten findet und feststellt, dass die Zeichenfolgen die gleiche Anzahl von Zeichen haben und daher gleich sind.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#144](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]

##  <a name="operator_gt"></a>  CStringT::operator &gt;

Bestimmt, ob die Zeichenfolge links vom Operator größer als die Zeichenfolge auf der rechten Seite ist.

```
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parameter

*str1*  
Ein `CStringT` für den Vergleich.

*str2*  
Ein `CStringT` für den Vergleich.

*psz1*  
Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.

*psz2*  
Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.

### <a name="remarks"></a>Hinweise

Ein lexikografischer Vergleich zwischen Zeichenfolgen Zeichen für Zeichen bis:

- Er zwei korrespondierende ungleiche Zeichen findet, und deren Vergleich als Ergebnis des Vergleichs zweier Zeichenfolgen genommen wird.

- Er keine Ungleichheiten findet, aber eine Zeichenfolge mehr Zeichen hat als die andere und die kürzere Zeichenfolge als kleiner als die längere Zeichenfolge betrachtet wird.

- Er keine Ungleichheiten findet und feststellt, dass die Zeichenfolgen die gleiche Anzahl von Zeichen haben und daher gleich sind.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#145](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]

##  <a name="operator_lt_eq"></a>  CStringT::operator &lt;=

Bestimmt, ob die Zeichenfolge links vom Operator kleiner als oder gleich der Zeichenfolge auf der rechten Seite ist.

```
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parameter

*str1*  
Ein `CStringT` für den Vergleich.

*str2*  
Ein `CStringT` für den Vergleich.

*psz1*  
Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.

*psz2*  
Ein Zeiger auf eine Null-terminierte Zeichenfolge für den Vergleich.

### <a name="remarks"></a>Hinweise

Ein lexikografischer Vergleich zwischen Zeichenfolgen Zeichen für Zeichen bis:

- Er zwei korrespondierende ungleiche Zeichen findet, und deren Vergleich als Ergebnis des Vergleichs zweier Zeichenfolgen genommen wird.

- Er keine Ungleichheiten findet, aber eine Zeichenfolge mehr Zeichen hat als die andere und die kürzere Zeichenfolge als kleiner als die längere Zeichenfolge betrachtet wird.

- Er keine Ungleichheiten findet und feststellt, dass die Zeichenfolgen die gleiche Anzahl von Zeichen haben und daher gleich sind.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#146](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]

##  <a name="operator_gt_eq"></a>  CStringT::operator &gt;=

Bestimmt, ob die Zeichenfolge links vom Operator größer als oder gleich der Zeichenfolge auf der rechten Seite ist.

```
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>Parameter

*str1*  
Ein `CStringT` für den Vergleich.

*str2*  
Ein `CStringT` für den Vergleich.

*psz1*  
Ein Zeiger auf eine Zeichenfolge für den Vergleich.

*psz2*  
Ein Zeiger auf eine Zeichenfolge für den Vergleich.

### <a name="remarks"></a>Hinweise

Ein lexikografischer Vergleich zwischen Zeichenfolgen Zeichen für Zeichen bis:

- Er zwei korrespondierende ungleiche Zeichen findet, und deren Vergleich als Ergebnis des Vergleichs zweier Zeichenfolgen genommen wird.

- Er keine Ungleichheiten findet, aber eine Zeichenfolge mehr Zeichen hat als die andere und die kürzere Zeichenfolge als kleiner als die längere Zeichenfolge betrachtet wird.

- Er keine Ungleichheiten findet und feststellt, dass die Zeichenfolgen die gleiche Anzahl von Zeichen haben und daher gleich sind.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#147](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]

##  <a name="remove"></a>  CStringT::Remove

Entfernt alle Instanzen des angegebenen Zeichens aus der Zeichenfolge.

```
int Remove(XCHAR chRemove);
```

### <a name="parameters"></a>Parameter

*chRemove*  
Das Zeichen aus einer Zeichenfolge entfernt werden soll.

### <a name="return-value"></a>Rückgabewert

Die Anzahl von Zeichen aus der Zeichenfolge entfernt. NULL, wenn die Zeichenfolge nicht geändert wird.

### <a name="remarks"></a>Hinweise

Vergleiche für das Zeichen werden die Groß-/Kleinschreibung beachtet.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#129](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]

##  <a name="replace"></a>  CStringT::Replace

Es gibt zwei Versionen der `Replace`. Die erste Version ersetzt eine oder mehrere Kopien einer Teilzeichenfolge durch eine andere Teilzeichenfolge. Beide Teilzeichenfolgen sind Null-terminiert. Die zweite Version ersetzt eine oder mehrere Kopien eines Zeichens durch ein anderes Zeichen. Beide Versionen ausgeführt werden, für die Zeichendaten in gespeicherten `CStringT`.

```
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```

### <a name="parameters"></a>Parameter

*pszOld*  
Ein Zeiger auf eine Null-terminierte Zeichenfolge durch ersetzt werden *PszNew*.

*pszNew*  
Ein Zeiger auf eine auf Null endende Zeichenfolge, die ersetzt *PszOld*.

*chOld*  
Das Zeichen zu ersetzen durch *ChNew*.

*chNew*  
Das Zeichen ersetzen *ChOld*.

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Instanzen ersetzt das Zeichen oder Teilzeichenfolge oder 0 (null) zurück, wenn die Zeichenfolge nicht geändert wird.

### <a name="remarks"></a>Hinweise

`Replace` die Länge der Zeichenfolge kann geändert werden, da *PszNew* und *PszOld* müssen nicht dieselbe Länge aufweisen und mehrere Kopien der alten Teilzeichenfolge in das neue Projekt geändert werden können. Die Funktion führt eine Übereinstimmung der Groß-/Kleinschreibung beachtet.

Beispiele für `CStringT` Instanzen sind `CString`, `CStringA`, und `CStringW`.

Für `CStringA`, `Replace` funktioniert mit ANSI oder Multibytezeichen (MBCS). Für `CStringW`, `Replace` arbeitet mit Breitzeichen.

Für `CString`, zum Zeitpunkt der Kompilierung der Zeichendatentyp ausgewählt ist, basierend auf, ob die Konstanten in der folgenden Tabelle definiert werden.

|Definierten Konstanten|Character-Datentyp|
|----------------------|-------------------------|
|_UNICODE|Breitzeichen|
|_MBCS|Multi-Byte-Zeichen|
|Weder|Einzelbyte-Zeichen|
|Beides|Nicht definiert|

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#200](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]

##  <a name="reversefind"></a>  CStringT::ReverseFind

Diese sucht `CStringT` -Objekt für die letzte Übereinstimmung eines Zeichens.

```
int ReverseFind(XCHAR ch) const throw();
```

### <a name="parameters"></a>Parameter

*ch*  
Das zu suchende Zeichen.

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index des letzten Zeichens in dieser `CStringT` -Objekt, das das angeforderte Zeichen oder -1 entspricht, wenn das Zeichen nicht gefunden wird.

### <a name="remarks"></a>Hinweise

Die Funktion ist vergleichbar mit der Run-Time-Funktion `strrchr`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#130](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]

##  <a name="right"></a>  CStringT::Right

Extrahiert die letzte (d. h. ganz rechts) *nCount* Zeichen aus diesem `CStringT` Objekt und gibt eine Kopie der extrahierten Teilzeichenfolge zurück.

```
CStringT Right(int nCount) const; 
```

### <a name="parameters"></a>Parameter

*nCount*  
Die Anzahl der aus diesem `CStringT`-Objekt zu extrahierenden Zeichen.

### <a name="return-value"></a>Rückgabewert

Ein `CStringT`-Objekt, das eine Kopie des angegebenen Zeichenbereichs enthält. Beachten Sie, dass die zurückgegebene `CStringT` Objekt kann leer sein.

### <a name="remarks"></a>Hinweise

Wenn *nCount* überschreitet die Länge der Zeichenfolge, und klicken Sie dann die gesamte Zeichenfolge extrahiert wird. `Right` wird der ähnlich wie der grundlegende `Right` funktionieren (außer, dass Indizes in Basic nullbasiert sind).

Für multibyte-Zeichensätze (MBCS), setzt *nCount* bezieht sich auf jedes 8-Bit-Zeichen, d. h. ein und die nachfolgenden Byte in einem multibyte-Zeichen werden als zwei Zeichen gezählt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#131](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]

##  <a name="setsysstring"></a>  CStringT::SetSysString

Das BSTR verweist zuordnet *Pbstr* und kopiert den Inhalt der `CStringT` Objekt ein, einschließlich NULL-Zeichen.

```
BSTR SetSysString(BSTR* pbstr) const; 
```

### <a name="parameters"></a>Parameter

*pbstr*  
Ein Zeiger auf eine Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Die neue Zeichenfolge.

### <a name="remarks"></a>Hinweise

Abhängig vom Inhalt der `CStringT` -Objekt, das den Wert des freizugebenden BSTR verweist *Pbstr* ändern können. Löst die Funktion eine `CMemoryException` Wenn nicht genügend Arbeitsspeicher vorhanden ist.

Diese Funktion wird normalerweise verwendet, um den Wert von Zeichenfolgen, die als Verweis übergeben wird, für die Automatisierung zu ändern.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#132](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]

##  <a name="spanexcluding"></a>  CStringT::SpanExcluding

Extrahiert Zeichen aus der Zeichenfolge, beginnend mit dem ersten Zeichen, die nicht in den Satz von Zeichen, die identifizierte *PszCharSet*.

```
CStringT SpanExcluding(PCXSTR pszCharSet) const; 
```

### <a name="parameters"></a>Parameter

*pszCharSet*  
Eine Zeichenfolge, die als eine Gruppe von Zeichen interpretiert werden.

### <a name="return-value"></a>Rückgabewert

Eine Teilzeichenfolge, die Zeichen in der Zeichenfolge enthält, die nicht in *PszCharSet*, mit dem ersten Zeichen in der Zeichenfolge beginnt und endet mit dem ersten Zeichen, die in der Zeichenfolge, die auch in gefunden *PszCharSet* (dabei ist das erste Zeichen in der Zeichenfolge und bis zum, jedoch ohne das erste Zeichen in der Zeichenfolge, die gefunden wird, also *PszCharSet*). Es gibt die gesamte Zeichenfolge zurück, wenn kein Zeichen in *PszCharSet* befindet sich in der Zeichenfolge.

### <a name="remarks"></a>Hinweise

`SpanExcluding` extrahiert und gibt alle Zeichen, die das erste Vorkommen eines Zeichens aus vorherigen *PszCharSet* (das heißt, das Zeichen aus *PszCharSet* und alle in der Zeichenfolge steht folgenden Zeichen sind nicht zurückgegeben). Wenn keine Zeichen aus *PszCharSet* befindet sich in der Zeichenfolge, dann `SpanExcluding` gibt die gesamte Zeichenfolge zurück.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#133](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]

##  <a name="spanincluding"></a>  CStringT::SpanIncluding

Extrahiert Zeichen aus der Zeichenfolge, beginnend mit dem ersten Zeichen, die in den Satz von Zeichen, die identifizierte sind *PszCharSet*.

```
CStringT SpanIncluding(PCXSTR pszCharSet) const; 
```

### <a name="parameters"></a>Parameter

*pszCharSet*  
Eine Zeichenfolge, die als eine Gruppe von Zeichen interpretiert werden.

### <a name="return-value"></a>Rückgabewert

Eine Teilzeichenfolge, die Zeichen in der Zeichenfolge, die in sind enthält *PszCharSet*, mit dem ersten Zeichen in der Zeichenfolge beginnt und endet, wenn ein Zeichen in der Zeichenfolge gefunden wurde, der nicht *PszCharSet*. `SpanIncluding` Gibt eine leere Teilzeichenfolge zurück, wenn das erste Zeichen in der Zeichenfolge nicht in der angegebenen Menge vorhanden ist.

### <a name="remarks"></a>Hinweise

Wenn das erste Zeichen der Zeichenfolge nicht klicken Sie dann in den Zeichensatz ist `SpanIncluding` eine leere Zeichenfolge zurückgegeben. Andernfalls wird eine Folge von aufeinander folgenden Zeichen, die in der Gruppe zurückgegeben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#134](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]

##  <a name="tokenize"></a>  CStringT::Tokenize

Sucht das nächste Token in eine Zielzeichenfolge

```
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const; 
```

### <a name="parameters"></a>Parameter

*pszTokens*  
Eine Zeichenfolge, die token-Trennzeichen enthält. Die Reihenfolge der diese Trennzeichen ist nicht wichtig.

*iStart*  
Der nullbasierte Index, um die Suche zu starten.

### <a name="return-value"></a>Rückgabewert

Ein `CStringT` -Objekt, das den aktuellen Tokenwert enthält.

### <a name="remarks"></a>Hinweise

Die `Tokenize` -Funktion sucht das nächste Token in der Zielzeichenfolge. Der Satz von Zeichen im *PszTokens* gibt mögliche Trennzeichen des Tokens gefunden werden. Bei jedem Aufruf `Tokenize` die Funktion beginnt am *iStart*, überspringt die vorangestellte Trennzeichen und gibt eine `CStringT` -Objekt, das das aktuelle Token und die ist die Zeichenfolge bis zum nächsten Trennzeichen enthält. Der Wert des *iStart* wird aktualisiert, um zu die Position, befolgen das schließende Trennzeichen oder -1, wenn das Ende der Zeichenfolge erreicht wurde. Weitere Token können geholt werden den Rest der Zielzeichenfolge durch eine Reihe von Aufrufen an `Tokenize`mit *iStart* zu verfolgen, an welcher Stelle der Zeichenfolge werden, dass das nächste Token gelesen werden. Wenn es keine weiteren Token sind wird die Funktion eine leere Zeichenfolge zurückgegeben und *iStart* wird auf-1 festgelegt.

Im Gegensatz zu der CRT mit Token zu versehen Funktionen wie [Strtok_s, _strtok_s_l, Wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md), `Tokenize` ändert sich nicht auf die Zielzeichenfolge.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#135](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]

### <a name="remarks"></a>Hinweise

In diesem Beispiel wird die Ausgabe lautet wie folgt aus:

```Output
Resulting Token: First
Resulting Token: Second
Resulting Token: Third
```

##  <a name="trim"></a>  CStringT::Trim

Entfernt führende und nachfolgende Zeichen aus der Zeichenfolge.

```
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```

### <a name="parameters"></a>Parameter

*chTarget*  
Das Ziel zu kürzenden Zeichen.

*pszTargets*  
Ein Zeiger auf eine Zeichenfolge mit dem Ziel zu kürzenden Zeichen. Alle führenden und nachgestellten Vorkommen der Zeichen im *PszTarget* abgeschnitten aus der `CStringT` Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt die Zeichenfolge mit abgetrenntem Leerraum zurück.

### <a name="remarks"></a>Hinweise

Entfernt alle führende und nachgestellte Vorkommen eines der folgenden:

- Durch angegebene Zeichen *ChTarget*.

- Alle Zeichen finden Sie in der angegebenen Zeichenfolge *PszTargets*.

- Leerzeichen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#136](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]

### <a name="remarks"></a>Hinweise

In diesem Beispiel wird die Ausgabe lautet wie folgt aus:

```Output
Before: "******Soccer is best, but liquor is quicker!!!!!"
After : "Soccer is best, but liquor is quicker"
```

##  <a name="trimleft"></a>  CStringT::TrimLeft

Entfernt die führenden Zeichen aus der Zeichenfolge.

```
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```

### <a name="parameters"></a>Parameter

*chTarget*  
Das Ziel zu kürzenden Zeichen.

*pszTargets*  
Ein Zeiger auf eine Zeichenfolge mit dem Ziel zu kürzenden Zeichen. Alle nachgestellten Vorkommen der Zeichen in *PszTarget* abgeschnitten aus der `CStringT` Objekt.

### <a name="return-value"></a>Rückgabewert

Die resultierende abgeschnittenen Zeichenfolge.

### <a name="remarks"></a>Hinweise

Entfernt alle führende und nachgestellte Vorkommen eines der folgenden:

- Durch angegebene Zeichen *ChTarget*.

- Alle Zeichen finden Sie in der angegebenen Zeichenfolge *PszTargets*.

- Leerzeichen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#137](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]

##  <a name="trimright"></a>  CStringT::TrimRight

Kürzt das nachfolgende Zeichen aus der Zeichenfolge.

```
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```

### <a name="parameters"></a>Parameter

*chTarget*  
Das Ziel zu kürzenden Zeichen.

*pszTargets*  
Ein Zeiger auf eine Zeichenfolge mit dem Ziel zu kürzenden Zeichen. Alle nachgestellten Vorkommen der Zeichen im *PszTarget* abgeschnitten aus der `CStringT` Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt die `CStringT` Objekt, das die Zeichenfolge mit abgetrenntem Leerraum enthält.

### <a name="remarks"></a>Hinweise

Entfernt die nachgestellten Vorkommen eines der folgenden:

- Durch angegebene Zeichen *ChTarget*.

- Alle Zeichen finden Sie in der angegebenen Zeichenfolge *PszTargets*.

- Leerzeichen.

Die `CStringT& TrimRight(XCHAR chTarget)` Version akzeptiert einen Zeichenparameter und entfernt alle Kopien dieses Zeichen vom Ende `CStringT` Zeichenfolgendaten. Es beginnt mit dem Ende der Zeichenfolge und funktioniert in Richtung Anfang. Es beendet, wenn sie ein anderes Zeichen findet oder wenn `CSTringT` nicht mehr genügend Zeichendaten enthalten sind.

Die `CStringT& TrimRight(PCXSTR pszTargets)` Version akzeptiert eine Null-terminierte Zeichenfolge, die alle für die Suche nach anderen Zeichen enthält. Entfernt alle Kopien dieser Zeichen in der `CStringT` Objekt. Es startet am Ende der Zeichenfolge und funktioniert nach vorn. Es beendet, wenn es sich um ein Zeichen findet, die nicht in der Zielzeichenfolge enthalten ist, oder wenn `CStringT` nicht mehr genügend Zeichendaten enthalten sind. Wird nicht versucht, eine Teilzeichenfolge am Ende die gesamten Zielzeichenfolge entspricht `CStringT`.

Die `CStringT& TrimRight()` Version sind keine Parameter erforderlich. Es entfernt alle nachgestellten Leerzeichen am Ende der `CStringT` Zeichenfolge. Leerzeichen können Zeilenumbrüche, Leerzeichen oder Tabstopps sein.

-

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#138](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)<br/>
[CSimpleStringT-Klasse](../../atl-mfc-shared/reference/csimplestringt-class.md)

