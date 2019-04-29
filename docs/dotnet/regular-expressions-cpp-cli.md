---
title: Reguläre Ausdrücke (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- regular expressions [C++]
- .NET Framework [C++], regular expressions
- regular expressions [C++], about regular expressions
- parsing strings [C++]
- examples [C++], strings
- regular expressions [C++], parsing strings
- Split method, parsing strings
- strings [C++], parsing
- substrings, simple matches
- searching, exact substring matches
- strings [C++], exact substring matching
- regular expressions [C++], simple matching
- IsMatch method
- strings [C++], extracting data from
- formatted strings [C++]
- regular expressions [C++], extracting data fields
- data [C++], extracting from strings
- regular expressions [C++], rearranging data
- data [C++], rearranging
- search and replace
- Replace method
- regular expressions [C++], search and replace
- strings [C++], formatting
- data [C++], formatting
- regular expressions [C++], validating data formatting
ms.assetid: 838bab49-0dbc-4089-a604-ef146269ef5a
ms.openlocfilehash: 24a278e4d5b208c5d8e3b95b9f5a0bd0306dbab3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384661"
---
# <a name="regular-expressions-ccli"></a>Reguläre Ausdrücke (C++/CLI)

Zeigt die verschiedener Zeichenfolgenoperationen mithilfe von Klassen für reguläre Ausdrücke in .NET Framework.

In den folgenden Themen veranschaulichen die Verwendung von .NET Framework <xref:System.Text.RegularExpressions> Namespace (und in einem Fall die <xref:System.String.Split%2A?displayProperty=fullName> Methode) zum Suchen, analysieren und Ändern von Zeichenfolgen.

## <a name="parse_regex"></a> Analysieren von Zeichenfolgen mithilfe von regulären Ausdrücken

Im folgenden Codebeispiel wird die einfache Zeichenfolgenanalyse mithilfe der <xref:System.Text.RegularExpressions.Regex>-Klasse im <xref:System.Text.RegularExpressions?displayProperty=fullName>-Namespace veranschaulicht. Eine Zeichenfolge mit mehreren Arten von Wortdelineatoren wird erstellt. Die Zeichenfolge wird dann mit der <xref:System.Text.RegularExpressions.Regex>-Klasse in Verbindung mit der <xref:System.Text.RegularExpressions.Match>-Klasse analysiert. Anschließend werden alle Wörter des Satzes getrennt angezeigt.

### <a name="example"></a>Beispiel

```cpp
// regex_parse.cpp
// compile with: /clr
#using <system.dll>

using namespace System;
using namespace System::Text::RegularExpressions;

int main( )
{
   int words = 0;
   String^ pattern = "[a-zA-Z]*";
   Console::WriteLine( "pattern : '{0}'", pattern );
   Regex^ regex = gcnew Regex( pattern );

   String^ line = "one\ttwo three:four,five six  seven";
   Console::WriteLine( "text : '{0}'", line );
   for( Match^ match = regex->Match( line );
        match->Success; match = match->NextMatch( ) )
   {
      if( match->Value->Length > 0 )
      {
         words++;
         Console::WriteLine( "{0}", match->Value );
      }
   }
   Console::WriteLine( "Number of Words : {0}", words );

   return 0;
}
```

## <a name="parse_split"></a> Analysieren von Zeichenfolgen mithilfe der Split-Methode

Im folgenden Codebeispiel wird die Verwendung der <xref:System.String.Split%2A?displayProperty=fullName>-Methode veranschaulicht, um alle Wörter einer Zeichenfolge zu extrahieren. Eine Zeichenfolge mit mehreren Arten von Wortdelineatoren wird generiert und dann durch Aufrufen von <xref:System.String.Split%2A> mit einer Liste der Delineatoren analysiert. Anschließend werden alle Wörter des Satzes getrennt angezeigt.

### <a name="example"></a>Beispiel

```cpp
// regex_split.cpp
// compile with: /clr
using namespace System;

int main()
{
   String^ delimStr = " ,.:\t";
   Console::WriteLine( "delimiter : '{0}'", delimStr );
   array<Char>^ delimiter = delimStr->ToCharArray( );
   array<String^>^ words;
   String^ line = "one\ttwo three:four,five six seven";

   Console::WriteLine( "text : '{0}'", line );
   words = line->Split( delimiter );
   Console::WriteLine( "Number of Words : {0}", words->Length );
   for (int word=0; word<words->Length; word++)
      Console::WriteLine( "{0}", words[word] );

   return 0;
}
```

## <a name="regex_simple"></a> Verwenden Sie regulärer Ausdrücke für einfache Gleichheitsprüfung

Das folgende Codebeispiel verwendet reguläre Ausdrücke nach Übereinstimmungen mit genauen Teilzeichenfolgen gesucht werden soll. Die Suche erfolgt von der statischen <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> Methode, die zwei Zeichenfolgen als Eingabe akzeptiert. Die erste ist die Zeichenfolge, die gesucht werden soll, und die zweite ist das Muster, nach dem gesucht werden.

### <a name="example"></a>Beispiel

```cpp
// regex_simple.cpp
// compile with: /clr
#using <System.dll>

using namespace System;
using namespace System::Text::RegularExpressions;

int main()
{
   array<String^>^ sentence =
   {
      "cow over the moon",
      "Betsy the Cow",
      "cowering in the corner",
      "no match here"
   };

   String^ matchStr = "cow";
   for (int i=0; i<sentence->Length; i++)
   {
      Console::Write( "{0,24}", sentence[i] );
      if ( Regex::IsMatch( sentence[i], matchStr,
                     RegexOptions::IgnoreCase ) )
         Console::WriteLine("  (match for '{0}' found)", matchStr);
      else
         Console::WriteLine("");
   }
   return 0;
}
```

## <a name="regex_extract"></a> Verwenden von regulären Ausdrücken zum Extrahieren von Datenfeldern

Das folgende Codebeispiel veranschaulicht die Verwendung von regulären Ausdrücken zum Extrahieren von Daten aus einer formatierten Zeichenfolge. Im folgenden Codebeispiel wird die <xref:System.Text.RegularExpressions.Regex> Klasse, um ein Muster anzugeben, die eine e-Mail-Adresse entspricht. Diese gehören Feldbezeichner, die verwendet werden können, um den Benutzer und Hostbereich jede e-Mail-Adresse abzurufen. Die <xref:System.Text.RegularExpressions.Match> Klasse wird verwendet, um die tatsächlichen Musterabgleich verwendet. Wenn die angegebene e-Mail-Adresse gültig ist, werden den Benutzernamen und Hostnamen extrahiert und angezeigt.

### <a name="example"></a>Beispiel

```cpp
// Regex_extract.cpp
// compile with: /clr
#using <System.dll>

using namespace System;
using namespace System::Text::RegularExpressions;

int main()
{
    array<String^>^ address=
    {
        "jay@southridgevideo.com",
        "barry@adatum.com",
        "treyresearch.net",
        "karen@proseware.com"
    };

    Regex^ emailregex = gcnew Regex("(?<user>[^@]+)@(?<host>.+)");

    for (int i=0; i<address->Length; i++)
    {
        Match^ m = emailregex->Match( address[i] );
        Console::Write("\n{0,25}", address[i]);

        if ( m->Success )
        {
            Console::Write("   User='{0}'",
            m->Groups["user"]->Value);
            Console::Write("   Host='{0}'",
            m->Groups["host"]->Value);
        }
        else
            Console::Write("   (invalid email address)");
        }

    Console::WriteLine("");
    return 0;
}
```

## <a name="regex_rearrange"></a> Verwenden von regulären Ausdrücken zum Neuanordnen von Daten

Im folgenden Codebeispiel wird veranschaulicht, wie die Unterstützung von regulären Ausdrücken .NET Framework neu anordnen und Formatieren von Daten verwendet werden kann. Im folgenden Codebeispiel wird die <xref:System.Text.RegularExpressions.Regex> und <xref:System.Text.RegularExpressions.Match> Klassen, die vor-und Nachnamen aus einer Zeichenfolge zu extrahieren, und klicken Sie dann diese Name-Elemente in umgekehrter Reihenfolge angezeigt.

Die <xref:System.Text.RegularExpressions.Regex> Klasse wird verwendet, um einen regulären Ausdruck zu erstellen, die das aktuelle Format der Daten beschreibt. Die beiden Namen können wird angenommen, dass durch ein Komma getrennt werden und eine beliebige Menge an Leerzeichen um Kommas herum. Die <xref:System.Text.RegularExpressions.Match> -Methode wird anschließend verwendet, um jede Zeichenfolge zu analysieren. Bei erfolgreicher Ausführung werden vor-und Nachnamen abgerufen, von der <xref:System.Text.RegularExpressions.Match> Objekt und angezeigt.

### <a name="example"></a>Beispiel

```cpp
// regex_reorder.cpp
// compile with: /clr
#using <System.dll>
using namespace System;
using namespace Text::RegularExpressions;

int main()
{
   array<String^>^ name =
   {
      "Abolrous, Sam",
      "Berg,Matt",
      "Berry , Jo",
      "www.contoso.com"
   };

   Regex^ reg = gcnew Regex("(?<last>\\w*)\\s*,\\s*(?<first>\\w*)");

   for ( int i=0; i < name->Length; i++ )
   {
      Console::Write( "{0,-20}", name[i] );
      Match^ m = reg->Match( name[i] );
      if ( m->Success )
      {
         String^ first = m->Groups["first"]->Value;
         String^ last = m->Groups["last"]->Value;
         Console::WriteLine("{0} {1}", first, last);
      }
      else
         Console::WriteLine("(invalid)");
   }
   return 0;
}
```

## <a name="regex_search"></a> Verwenden von regulären Ausdrücken zum Suchen und ersetzen

Im folgenden Codebeispiel wird veranschaulicht, wie die Klasse regulärer Ausdrücke <xref:System.Text.RegularExpressions.Regex> kann verwendet werden, suchen und Ersetzen Sie dies durchgeführt. Dies erfolgt mit der <xref:System.Text.RegularExpressions.Regex.Replace%2A> Methode. Die verwendete Version wird von zwei Zeichenfolgen als Eingabe: die Zeichenfolge, die geändert werden, und die Zeichenfolge, die anstelle der in den Abschnitten (sofern vorhanden) eingefügt werden soll, die dem Muster entsprechen, gewährt die <xref:System.Text.RegularExpressions.Regex> Objekt.

Dieser Code ersetzt alle Ziffern, die sich in einer Zeichenfolge durch Unterstriche (_) und dann ersetzt, die mit einer leeren Zeichenfolge, die sie tatsächlich entfernen. Die gleiche Wirkung kann in einem einzigen Schritt erfolgen, aber zwei Schritte werden hier zur Veranschaulichung verwendet.

### <a name="example"></a>Beispiel

```cpp
// regex_replace.cpp
// compile with: /clr
#using <System.dll>
using namespace System::Text::RegularExpressions;
using namespace System;

int main()
{
   String^ before = "The q43uick bro254wn f0ox ju4mped";
   Console::WriteLine("original  : {0}", before);

   Regex^ digitRegex = gcnew Regex("(?<digit>[0-9])");
   String^ after = digitRegex->Replace(before, "_");
   Console::WriteLine("1st regex : {0}", after);

   Regex^ underbarRegex = gcnew Regex("_");
   String^ after2 = underbarRegex->Replace(after, "");
   Console::WriteLine("2nd regex : {0}", after2);

   return 0;
}
```

## <a name="regex_validate"></a> Verwenden von regulären Ausdrücken, die Überprüfung der Datenformatierung

Das folgende Codebeispiel veranschaulicht die Verwendung von regulären Ausdrücken, um zu überprüfen, ob die Formatierung der Zeichenfolge. Das folgende Codebeispiel zeigt sollte die Zeichenfolge eine gültige Telefonnummer enthalten. Das folgende Codebeispiel verwendet die Zeichenfolge "\d{3}-\d{3}-\d{4}", um anzugeben, dass jedes Feld eine gültige Telefonnummer darstellt. In der Zeichenfolge "d" gibt an, eine Ziffer, und das Argument nach jedes "d" gibt die Anzahl der Ziffern, die vorhanden sein muss. In diesem Fall muss die Anzahl durch Bindestriche voneinander getrennt werden.

### <a name="example"></a>Beispiel

```cpp
// regex_validate.cpp
// compile with: /clr
#using <System.dll>

using namespace System;
using namespace Text::RegularExpressions;

int main()
{
   array<String^>^ number =
   {
      "123-456-7890",
      "444-234-22450",
      "690-203-6578",
      "146-893-232",
      "146-839-2322",
      "4007-295-1111",
      "407-295-1111",
      "407-2-5555",
   };

   String^ regStr = "^\\d{3}-\\d{3}-\\d{4}$";

   for ( int i = 0; i < number->Length; i++ )
   {
      Console::Write( "{0,14}", number[i] );

      if ( Regex::IsMatch( number[i], regStr ) )
         Console::WriteLine(" - valid");
      else
         Console::WriteLine(" - invalid");
   }
   return 0;
}
```

## <a name="related-sections"></a>Verwandte Abschnitte

[Reguläre Ausdrücke von .NET Framework](/dotnet/standard/base-types/regular-expressions)

## <a name="see-also"></a>Siehe auch

[.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
