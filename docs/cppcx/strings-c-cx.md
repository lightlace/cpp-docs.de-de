---
title: "Zeichenfolgen (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5b34e1df-7c2b-4269-aba8-b767d36c49d9
caps.latest.revision: 22
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 22
---
# Zeichenfolgen (C++/CX)
Text in [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] wird in [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] durch die [Platform::String\-Klasse](../cppcx/platform-string-class.md) dargestellt. Verwenden Sie die `Platform::String Class`, wenn Sie Zeichenfolgen hin und her an Methoden in [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Klassen übergeben oder wenn Sie mit anderen [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponenten über die Grenze der Anwendungsbinärschnittstelle \(ABI\) hinaus interagieren. Die `Platform::String Class` stellt Methoden für einige allgemeine Zeichenfolgenoperationen bereit, aber sie ist nicht als umfassende Zeichenfolgenklasse gedacht. Verwenden Sie in Ihrem C\+\+\-Modul Standard\-C\+\+\-Zeichenfolgentypen wie [wstring](../Topic/wstring.md) für sämtliche wesentliche Textverarbeitung und konvertieren Sie dann das Endergebnis zu [Platform::String](../cppcx/platform-string-class.md), bevor Sie es zu oder von einer öffentlichen Schnittstelle übergeben. Das Konvertieren zwischen `wstring` oder `wchar_t*` und `Platform::String` ist einfach und effizient.  
  
 **Fastpass**  
  
 In einigen Fällen kann der Compiler überprüfen, ob er eine `Platform::String` sicher erstellen oder eine `String` an eine Funktion übergeben werden kann, ohne die zugrunde liegenden Zeichenfolgendaten zu kopieren. Solche Vorgänge werden als *Fast Pass* bezeichnet und sie treten transparent auf.  
  
## Zeichenfolgenkonstruktion  
 Der Wert eines `String`\-Objekts ist eine unveränderliche \(schreibgeschützte\) Sequenz von `char16` \(16\-Bit\-Unicode\)\-Zeichen. Da ein `String`\-Objekt unveränderlich ist, ersetzt die Zuweisung eines neuen Zeichenfolgenliterals zu einer `String`\-Variable tatsächlich das ursprüngliche `String`\-Objekt durch ein neues `String`\-Objekt. Verkettungsvorgänge umfassen die Zerstörung des ursprünglichen `String`\-Objekts und die Erstellung eines neuen Objekts.  
  
 **Literale**  
  
 Ein *Literalzeichen* ist ein Zeichen, das in einfache Anführungszeichen eingeschlossen ist, und eine *Literalzeichenfolge* ist eine Sequenz von Zeichen, die in Anführungszeichen eingeschlossen ist. Wenn Sie ein Literal verwenden, um eine String^\-Variable zu initialisieren, nimmt der Compiler an, dass das Literal aus `char16`\-Zeichen besteht. Das heißt, dem Literal muss kein „L“\-Zeichenfolgenmodifizierer vorausgehen und es muss nicht in einem **\_T\(\)** oder **TEXT\(\)**\-Makro eingeschlossen werden. Weitere Informationen zur C\+\+\-Unterstützung für Unicode finden Sie unter [Zusammenfassung der Unicode\-Programmierung](../text/unicode-programming-summary.md).  
  
 Im folgenden Beispiel werden verschiedene Möglichkeiten veranschaulicht, um `String`\-Objekte zu erstellen.  
  
 [!code-cpp[cx_strings#01](../snippets/cpp/VS_Snippets_Misc/cx_strings/cpp/class1.cpp#01)]  
  
## Zeichenfolgenbehandlungsvorgänge  
 Die `String`\-Klasse stellt Methoden und Operatoren für das Verketten bereit und vergleicht Zeichenfolgen und andere grundlegender Zeichenfolgenoperationen. Um umfangreichere Zeichenfolgenbearbeitungen auszuführen, verwenden Sie die `String::Data()`\-Memberfunktion um den Wert des `String^`\-Objekts als `const wchar_t*` abzurufen. Verwenden Sie dann diesen Wert, um `std::wstring` zu initialisieren, der umfangreiche Funktionen für die Zeichenfolgenbehandlung bereitstellt.  
  
 [!code-cpp[cx_strings#03](../snippets/cpp/VS_Snippets_Misc/cx_strings/cpp/class1.cpp#03)]  
  
## Zeichenfolgenkonvertierung  
 Eine `Platform::String` kann nur `char16`\-Zeichen oder das `NULL`\-Zeichen enthalten. Wenn Ihre Anwendung mit 8\-Bit\-Zeichen funktionieren muss, verwenden Sie [String::Data\-Methode](../cppcx/string-data-method.md), um den Text als `const wchar_t*` zu extrahieren. Sie können dann die entsprechenden Windows\-Funktionen oder Standardbibliotheksfunktionen verwenden, um die Daten zu bearbeiten und sie zurück zu einer `wchar_t*` oder [wstring](../Topic/wstring.md) zu konvertieren. Diese können Sie dann verwenden, um neue `Platform::String` zu erstellen.  
  
 Das folgende Codefragment zeigt, wie eine `String^`\-Variable in eine und aus einer `wstring`\-Variable konvertiert wird. Weitere Informationen zu der in diesem Beispiel verwendeten Zeichenfolgenbearbeitung finden Sie unter [basic\_string::replace](../Topic/basic_string::replace.md).  
  
 [!code-cpp[cx_strings#04](../snippets/cpp/VS_Snippets_Misc/cx_strings/cpp/class1.cpp#04)]  
  
## Zeichenfolgenlänge und eingebettete NULL\-Werte  
 Die [String::Length\-Methode](../cppcx/string-length-method.md) gibt die Anzahl von Zeichen in der Zeichenfolge, nicht die Anzahl von Bytes zurück. Das abschließende NULL\-Zeichen wird nicht gezählt, es sei denn, Sie geben es explizit an, wenn Sie mithilfe von Stapelsemantik eine Zeichenfolge erstellen.  
  
 Eine `Platform::String` kann eingebettete NULL\-Werte enthalten, jedoch nur, wenn die NULL ein Ergebnis eines Verkettungsvorgangs ist. Eingebettete NULLEN werden in Zeichenfolgenliteralen nicht unterstützt. Daher können Sie eingebettete NULLEN nicht in dieser Weise verwenden, um eine `Platform::String` zu initialisieren. Eingebettete NULL\-Werte in einer `Platform::String` werden ignoriert, wenn die Zeichenfolge angezeigt wird, beispielsweise wenn sie einer `TextBlock::Text`\-Eigenschaft zugewiesen ist. Eingebettete NULL\-Werte werden entfernt, wenn der Zeichenfolgenwert von der `Data`\-Eigenschaft zurückgegeben wird.  
  
## StringReference  
 In einigen Fällen empfängt der Code \(a\) eine std::wstring\- oder wchar\_t\-Zeichenfolge oder ein L””\-Zeichenfolgenliteral und übergibt diese nur an eine andere Methode, die einen String^ als Eingabeparameter akzeptiert. Solange der ursprüngliche Zeichenfolgenpuffer selbst gültig bleibt und nicht geändert wird, bevor die Funktion zurückgibt, können Sie die `wchar_t*`\-Zeichenfolge oder das Zeichenfolgenliteral in [Platform::StringReference](../cppcx/platform-stringreference-class.md) konvertieren und dieses anstelle von `Platform::String^` übergeben. Dies ist zulässig, da `StringReference` über eine benutzerdefinierte Konvertierung zu `Platform::String^` verfügt. Mit `StringReference` können Sie vermeiden, dass eine zusätzliche Kopie der Zeichenfolgendaten erstellt wird. In Schleifen, in denen viele Zeichenfolgen übergeben werden, oder wenn sehr große Zeichenfolgen übergeben werden, können Sie mit `StringReference` eine deutliche Leistungsverbesserung erzielen. Aber, da `StringReference` im Grunde den ursprünglichen Zeichenfolgenpuffer verwendet, müssen Sie sorgfältig sein, um Speicherbeschädigungen zu vermeiden. Sie sollten `StringReference` nicht an eine asynchrone Methode übergeben, es sei denn, die ursprüngliche Zeichenfolge liegt garantiert im Bereich, wenn diese Methode zurückgibt. Ein String^, das von einem StringReference initialisiert wird, erzwingt eine Zuordnung und eine Kopie der Zeichenfolgendaten, wenn ein zweiter Zuweisungsvorgang auftritt. In diesem Fall verlieren Sie den Leistungsvorteil von `StringReference`.  
  
 Beachten Sie, dass `StringReference` ein Standard\-C\+\+\-Klassentyp und keine Verweisklasse ist. Sie können ihn nicht für die öffentliche Schnittstelle von Verweisklassenverwenden, die Sie definieren.  
  
 Im folgenden Beispiel wird die Verwendung von StringReference veranschaulicht:  
  
```  
void GetDecodedStrings(std::vector<std::wstring> strings)  
{  
    using namespace Windows::Security::Cryptography;  
    using namespace Windows::Storage::Streams;  
  
    for (auto&& s : strings)  
    {  
        // Method signature is IBuffer^ CryptographicBuffer::DecodeFromBase64String (Platform::String^)  
        // Call using StringReference:  
        IBuffer^ buffer = CryptographicBuffer::DecodeFromBase64String(StringReference(s.c_str()));  
  
        //...do something with buffer  
    }  
}  
```  
  
## Siehe auch  
 [Built\-in Types](http://msdn.microsoft.com/de-de/acc196fd-09da-4882-b554-6c94685ec75f)