---
title: "CStringT Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CString"
  - "CStringT"
  - "ATL::CStringT"
  - "ATL.CStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringT class"
  - "shared classes, CStringT"
  - "Zeichenfolgen [C++], in ATL"
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
caps.latest.revision: 33
caps.handback.revision: "22"
ms.author: "mblome"
manager: "ghogen"
---
# CStringT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt ein `CStringT`\-Objekt dar.  
  
## Syntax  
  
```  
  
      template< typename   
      BaseType  
      , class   
      StringTraits  
       >  
class CStringT :   
public CSimpleStringT<   BaseType,   _CSTRING_IMPL_::_MFCDLLTraitsCheck<      BaseType,      StringTraits   >   ::c_bIsMFCDLLTraits>  
```  
  
#### Parameter  
 `BaseType`  
 Der Zeichentyp der Zeichenfolgenklasse.  Einer der folgenden Werte ist möglich:  
  
-   `char` \(für ANSI\-Zeichenfolgen\).  
  
-   `wchar_t` \(für Unicode\-Zeichenfolgen\).  
  
-   **TCHAR** \(für ANSI und Unicode\-Zeichenfolgen\).  
  
 `StringTraits`  
 Bestimmt, ob die Zeichenfolgenklasse Bibliotheksunterstützung der C\-Laufzeit\-\(CRT\) erfordert und wo Zeichenfolgenressourcen lokalisiert werden.  Einer der folgenden Werte ist möglich:  
  
-   **StrTraitATL\<\-wchar t** &#124; `char` &#124; **TCHAR, ChTraitsCRT\<\-wchar t** &#124; `char` &#124; **TCHAR \> \>**  
  
     Die Klasse benötigt CRT\-Unterstützung und Datenbanksuchen für Ressourcenzeichenfolgen im Modul, das von `m_hInstResource` angegeben wird \(Mitglied der Applikationsmodulklasse\).  
  
-   **StrTraitATL\<\-wchar t** &#124; `char` &#124; **TCHAR, ChTraitsOS\<\-wchar t** &#124; `char` &#124; **TCHAR \> \>**  
  
     Die Klasse ist nicht CRT\-Unterstützung und Datenbanksuchen für Ressourcenzeichenfolgen im Modul, das von `m_hInstResource` angegeben wird \(Mitglied der Applikationsmodulklasse\).  
  
-   **StrTraitMFC\<\-wchar t** &#124; `char` &#124; **TCHAR, ChTraitsCRT\<\-wchar t** &#124; `char` &#124; **TCHAR \> \>**  
  
     Die Klasse benötigt CRT\-Unterstützung und Datenbanksuchen für Ressourcenzeichenfolgen mithilfe des Suchalgorithmus mit MFC.  
  
-   **StrTraitMFC\<\-wchar t** &#124; `char` &#124; **TCHAR, ChTraitsOS\<\-wchar t** &#124; `char` &#124; **TCHAR \> \>**  
  
     Die Klasse benötigt CRT\-Unterstützung und Datenbanksuchen für Ressourcenzeichenfolgen nicht mithilfe des Suchalgorithmus mit MFC.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CStringT::CStringT](../Topic/CStringT::CStringT.md)|Erstellt ein Objekt `CStringT` auf verschiedene Arten.|  
|[CStringT::~CStringT](../Topic/CStringT::~CStringT.md)|Zerstört ein `CStringT`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CStringT::AllocSysString](../Topic/CStringT::AllocSysString.md)|Ordnet `BSTR` von `CStringT` Daten.|  
|[CStringT::AnsiToOem](../Topic/CStringT::AnsiToOem.md)|Führt eine direkte Konvertierung vom ANSI\-Zeichensatz zum OEM\-Zeichensatz.|  
|[CStringT::AppendFormat](../Topic/CStringT::AppendFormat.md)|Appends formatierte Daten zu einem vorhandenen `CStringT`\-Objekt.|  
|[CStringT::Collate](../Topic/CStringT::Collate.md)|Vergleicht zwei Zeichenfolgen \(Groß\-\/Kleinschreibung, gebietsschemaspezifische Informationen der Verwendung\).|  
|[CStringT::CollateNoCase](../Topic/CStringT::CollateNoCase.md)|Vergleicht zwei Zeichenfolgen \(die Groß\-\/Kleinschreibung nicht beachtet, gebietsschemaspezifische Informationen der Verwendung\).|  
|[CStringT::Compare](../Topic/CStringT::Compare.md)|Vergleicht zwei Zeichenfolgen \(Groß\-\/Kleinschreibung beachten\).|  
|[CStringT::CompareNoCase](../Topic/CStringT::CompareNoCase.md)|Vergleicht zwei Zeichenfolgen \(Kleinschreibung\).|  
|[CStringT::Delete](../Topic/CStringT::Delete.md)|Löscht ein Zeichen oder Zeichen aus einer Zeichenfolge.|  
|[CStringT::Find](../Topic/CStringT::Find.md)|Sucht ein Zeichen oder einer Teilzeichenfolge in einer größeren Zeichenfolge.|  
|[CStringT::FindOneOf](../Topic/CStringT::FindOneOf.md)|Sucht das erste übereinstimmende Zeichen aus einem Satz.|  
|[CStringT::Format](../Topic/CStringT::Format.md)|Formatiert die Zeichenfolge, wie `sprintf` ausführt.|  
|[CStringT::FormatMessage](../Topic/CStringT::FormatMessage.md)|Formatiert eine Meldungszeichenfolge.|  
|[CStringT::FormatMessageV](../Topic/CStringT::FormatMessageV.md)|Formatiert eine Meldungszeichenfolge mithilfe einer Variablenargumentlisten.|  
|[CStringT::FormatV](../Topic/CStringT::FormatV.md)|Formatiert die Zeichenfolge mit einer variablen Liste der Argumente.|  
|[CStringT::GetEnvironmentVariable](../Topic/CStringT::GetEnvironmentVariable.md)|Legt die Zeichenfolge an den Wert der angegebenen Umgebungsvariablen fest.|  
|[CStringT::Insert](../Topic/CStringT::Insert.md)|Fügt ein einzelnes Zeichen oder eine Teilzeichenfolge am angegebenen Index in der Zeichenfolge ein.|  
|[CStringT::Left](../Topic/CStringT::Left.md)|Gibt den linken Teil einer Zeichenfolge.|  
|[CStringT::LoadString](../Topic/CStringT::LoadString.md)|Lädt ein vorhandenes `CStringT`\-Objekt von einer Windows.|  
|[CStringT::MakeLower](../Topic/CStringT::MakeLower.md)|Konvertiert alle Zeichen in dieser Zeichenfolge mit den Kleinbuchstaben.|  
|[CStringT::MakeReverse](../Topic/CStringT::MakeReverse.md)|Gibt die Zeichenfolge um.|  
|[CStringT::MakeUpper](../Topic/CStringT::MakeUpper.md)|Konvertiert alle Zeichen in dieser Zeichenfolge in Großbuchstaben um.|  
|[CStringT::Mid](../Topic/CStringT::Mid.md)|Gibt den mittleren Teil einer Zeichenfolge.|  
|[CStringT::OemToAnsi](../Topic/CStringT::OemToAnsi.md)|Führt eine direkte Konvertierung vom OEM\-Zeichensatz zum ANSI\-Zeichensatz.|  
|[CStringT::Remove](../Topic/CStringT::Remove.md)|Entfernt angegebene Zeichen aus einer Zeichenfolge.|  
|[CStringT::Replace](../Topic/CStringT::Replace.md)|Replaces gab Zeichen mit anderen Zeichen.|  
|[CStringT::ReverseFind](../Topic/CStringT::ReverseFind.md)|Sucht ein Zeichen in einer größeren Zeichenfolge; ausgehend vom Ende ab.|  
|[CStringT::Right](../Topic/CStringT::Right.md)|Gibt den rechten Teil einer Zeichenfolge.|  
|[CStringT::SetSysString](../Topic/CStringT::SetSysString.md)|Legt ein vorhandenes `BSTR`\-Objekt mit Daten von einem `CStringT`\-Objekt fest.|  
|[CStringT::SpanExcluding](../Topic/CStringT::SpanExcluding.md)|Extrahiert Zeichen aus der Zeichenfolge, beginnend mit dem ersten Zeichen, die nicht im Satz von Zeichen sind, die durch `pszCharSet` identifiziert werden.|  
|[CStringT::SpanIncluding](../Topic/CStringT::SpanIncluding.md)|Gibt eine Teilzeichenfolge, die nur die Zeichen in einem Satz enthält.|  
|[CStringT::Tokenize](../Topic/CStringT::Tokenize.md)|Auszüge angegebene Token in einer Zielzeichenfolge.|  
|[CStringT::Trim](../Topic/CStringT::Trim.md)|Schneidet alle führenden und nachgestellten Leerraumzeichen von der Zeichenfolge.|  
|[CStringT::TrimLeft](../Topic/CStringT::TrimLeft.md)|Ordnungen Leerraumzeichen, die aus der Zeichenfolge übergeben.|  
|[CStringT::TrimRight](../Topic/CStringT::TrimRight.md)|Ordnungen Leerraumzeichen, die aus der Zeichenfolge schleppen.|  
  
### Operatoren  
  
|||  
|-|-|  
|[CStringT::operator \=](../Topic/CStringT::operator%20=.md)|Weist einen neuen Wert zu einem `CStringT`\-Objekt zu.|  
|[CStringT::operator \+](../Topic/CStringT::operator%20+.md)|Verkettet zwei Zeichenfolgen oder ein Zeichen und eine Zeichenfolge.|  
|[CStringT::operator \+\=](../Topic/CStringT::operator%20+=.md)|Verkettet eine neue Zeichenfolge am Ende einer vorhandenen Zeichenfolge.|  
|[CStringT::operator \=\=](../Topic/CStringT::operator%20==.md)|Bestimmt, ob zwei Zeichenfolgen logisch gleich sind.|  
|[CStringT::operator \!\=](../Topic/CStringT::operator%20!=.md)|Bestimmt, ob zwei Zeichenfolgen logisch nicht gleich sind.|  
|[CStringT::operator \<](../Topic/CStringT::operator%20%3C.md)|Bestimmt, ob die Zeichenfolge auf der linken Seite des Operators kleiner als zur Zeichenfolge auf der rechten Seite ist.|  
|[CStringT::operator \>](../Topic/CStringT::operator%20%3E.md)|Bestimmt, ob die Zeichenfolge auf der linken Seite des Operators größer als zur Zeichenfolge auf der rechten Seite ist.|  
|[CStringT::operator \<\=](../Topic/CStringT::operator%20%3C=.md)|Bestimmt, ob die Zeichenfolge auf der linken Seite des Operators kleiner oder gleich der Zeichenfolge auf der rechten Seite ist.|  
|[CStringT::operator \>\=](../Topic/CStringT::operator%20%3E=.md)|Bestimmt, ob die Zeichenfolge auf der linken Seite des Operators größer oder gleich der Zeichenfolge auf der rechten Seite ist.|  
  
## Hinweise  
 `CStringT` erbt von [CSimpleStringT\-Klasse](../../atl-mfc-shared/reference/csimplestringt-class.md).  Erweiterte Funktionen, z Zeichenmanipulation, Reihenfolge und Suchen, werden durch `CStringT` implementiert.  
  
> [!NOTE]
>  `CStringT`\-Objekte sind zum Auslösen von Ausnahmen anzeigen.  Dies tritt wenn die `CStringT`\-Objekt wird auf, die für jeden Grund aufgrund ungenügenden Arbeitsspeichers sind.  
  
 Ein Objekt `CStringT` besteht aus einer Sequenz mit variabler Länge von Zeichen.  `CStringT` bietet Funktionen und Operatoren, die die Syntax verwenden, die der von Basic ähnelt.  Verkettung und Vergleichsoperatoren, zusammen mit vereinfachter Speicherverwaltung, machen `CStringT`\-Objekte einfacher als gewöhnliche Zeichenarrays zu verwenden.  
  
> [!NOTE]
>  Obwohl es möglich ist, `CStringT`\-Instanzen zu erstellen, die eingebettete NULL\-Zeichen aufweisen, empfiehlt es sich für diese.  Aufrufen von Methoden und Operatoren auf `CStringT`\-Objekten, die eingebettete NULL\-Zeichen aufweisen, können zu unerwarteten Ergebnissen führen.  
  
 Indem sie unterschiedliche Kombinationen der `BaseType` und `StringTraits`\-Parameter verwenden, können `CStringT`\-Objekte in die folgenden Typen stammen, die sind vordefiniert wurde durch die ATL\-Bibliotheken sind.  
  
 Bei Verwendung von in einer ATL\-Anwendung:  
  
 `CString`, `CStringA` und `CStringW` werden von der MFC\-DLL \(MFC90.DLL\), nie vom Benutzer DLL exportiert.  Dies geschieht, um zu verhindern, dass `CStringT` mehrfach definiert ist.  
  
> [!NOTE]
>  Wenn Sie Linkerfehler als, antrafen `CString` Exportieren von abgeleitete Klasse von einer MFC\-Erweiterungs\-DLL in Visual C\+\+ .NET 2002 und die Problemumgehung angewendet haben, wie im Knowledge Base\-Artikel beschrieben, "Fehler, wenn Sie CString\-Abgeleitete Klassen" \(importieren Q309801\), sollten Sie den geeigneten Problemumgehungscode entfernen, da dies in Visual C\+\+ .NET 2003 behoben wurde.  Knowledge Base\-Artikel finden Sie auf der MSDN Library\-CD\-ROM oder unter [http:\/\/support.microsoft.com\/default.aspx](http://support.microsoft.com/default.aspx).  
  
 Die folgenden Zeichenfolgentypen sind innerhalb der MFC\-basierten Anwendungen verfügbar:  
  
|CStringT\-Typ|Deklaration|  
|-------------------|-----------------|  
|`CStringA`|Eine ANSI\-Zeichen\-Typzeichenfolge mit CRT\-Unterstützung.|  
|`CStringW`|Eine Unicode\-Zeichentypzeichenfolge mit CRT\-Unterstützung.|  
|`CString`|ANSI\- und Unicode\-Schrifttypen mit CRT\-Unterstützung.|  
  
 Die folgenden Zeichenfolgentypen sind in den Projekten, in denen **ATL\_CSTRING\_NO\_CRT** definiert ist:  
  
|CStringT\-Typ|Deklaration|  
|-------------------|-----------------|  
|**CAtlStringA**|Eine ANSI\-Zeichen\-Typzeichenfolge ohne CRT\-Unterstützung.|  
|**CAtlStringW**|Eine Unicode\-Zeichentypzeichenfolge ohne CRT\-Unterstützung.|  
|**CAtlString**|ANSI\- und Unicode\-Schrifttypen ohne CRT\-Unterstützung.|  
  
 Die folgenden Zeichenfolgentypen sind in den Projekten, in denen **ATL\_CSTRING\_NO\_CRT** nicht definiert ist:  
  
|CStringT\-Typ|Deklaration|  
|-------------------|-----------------|  
|**CAtlStringA**|Eine ANSI\-Zeichen\-Typzeichenfolge mit CRT\-Unterstützung.|  
|**CAtlStringW**|Eine Unicode\-Zeichentypzeichenfolge mit CRT\-Unterstützung.|  
|**CAtlString**|ANSI\- und Unicode\-Schrifttypen mit CRT\-Unterstützung.|  
  
 `CString`\-Objekte sind außerdem die folgenden Eigenschaften:  
  
-   `CStringT`\-Objekte können aufgrund der Verkettungsvorgänge wachsen.  
  
-   `CStringT`\-Objekte folgen "Wertsemantik bezeichnet." Wägen Sie ein `CStringT`\-Objekt als tatsächliche Zeichenfolge, nicht als Zeiger auf eine Zeichenfolge.  
  
-   Sie können `CStringT`\-Objekte für `PCXSTR`\-Funktionsargumente frei ersetzen.  
  
-   Benutzerdefinierte Speicherverwaltung für Zeichenfolgenpuffer.  Weitere Informationen finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## CStringT definierte Typen vor  
 Da `CStringT` ein Vorlagenargument verwendet, um zu definieren, der nicht unterstützte \(entweder [wchar\_t](../../c-runtime-library/standard-types.md) oder [char](../../c-runtime-library/standard-types.md)\-Methodenparametertypen\), kann manchmal erschwert werden.  Um dieses Problem zu vereinfachen, wird ein Satz vordefinierter Typen während der `CStringT`\-Klasse definiert und verwendet.  In der folgenden Tabelle sind die verschiedenen Typen auf:  
  
|Name|Description|  
|----------|-----------------|  
|`XCHAR`|Ein einzelnes Zeichen \(entweder `wchar_t` oder `char`\) mit demselben Zeichentyp wie das `CStringT`\-Objekt.|  
|**YCHAR**|Ein einzelnes Zeichen \(entweder `wchar_t` oder `char`\) mit dem gegenüberliegenden Zeichentyp als dem `CStringT`\-Objekt.|  
|`PXSTR`|Ein Zeiger auf eine Zeichenfolge \(entweder `wchar_t` oder `char`\) mit demselben Zeichentyp wie das `CStringT`\-Objekt.|  
|**PYSTR**|Ein Zeiger auf eine Zeichenfolge \(entweder `wchar_t` oder `char`\) mit dem gegenüberliegenden Zeichentyp als dem `CStringT`\-Objekt.|  
|`PCXSTR`|Ein Zeiger auf eine Zeichenfolge **const** \(entweder `wchar_t` oder `char`\) mit demselben Zeichentyp wie das `CStringT`\-Objekt.|  
|**PCYSTR**|Ein Zeiger auf eine Zeichenfolge **const** \(entweder `wchar_t` oder `char`\) mit dem gegenüberliegenden Zeichentyp als dem `CStringT`\-Objekt.|  
  
> [!NOTE]
>  Code, dass zuvor verwendete nicht dokumentierten Methoden von `CString` \(z **AssignCopy**\) durch Code ersetzt werden müssen, der die folgenden dokumentierten Methoden von `CStringT` verwendet \(z `GetBuffer` oder `ReleaseBuffer`\).  Diese Methoden werden von `CSimpleStringT` geerbt.  
  
## Vererbungshierarchie  
 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)  
  
 `CStringT`  
  
## Anforderungen  
  
|Header|Verwendungszweck|  
|------------|----------------------|  
|cstringt.h|nur für MFC Zeichenfolgenobjekte|  
|atlstr.h|Zeichenfolgenobjekte MFC\-fremde|  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)   
 [CSimpleStringT Class](../../atl-mfc-shared/reference/csimplestringt-class.md)