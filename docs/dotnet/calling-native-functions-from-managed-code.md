---
title: "Aufrufen systemeigener Funktionen aus verwaltetem Code | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Aufrufen systemeigener Funktionen aus verwaltetem Code"
  - "Interop [C++], Aufrufen systemeigener Funktionen aus verwaltetem Code"
  - "Interoperabilität [C++], Aufrufen systemeigener Funktionen aus verwaltetem Code"
  - "Verwalteter Code [C++], Interoperabilität"
  - "Aufrufen systemeigener Funktionen aus verwaltetem Code [C++]"
  - "Plattformaufruf [C++], Interoperabilität"
ms.assetid: 982cef18-20d9-42b4-8242-a77fa65f2e36
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# Aufrufen systemeigener Funktionen aus verwaltetem Code
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Common Language Runtime stellt Platform Invocation Services, oder PInvoke, zur Verfügung, wodurch verwalteter Code Funktionen in C\-Format in systemeigenen DLLs \(Dynamic Link Libraries\) aufrufen kann.  Hierbei wird das gleiche Datenmarshalling verwendet wie für die COM\-Interoperabilität mit der Laufzeit und für den IJW \("It Just Works"\)\-Mechanismus.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Verwenden von explizitem PInvoke in C\+\+ \(DllImport\-Attribut\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)  
  
-   [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [A Closer Look at Platform Invoke](assetId:///ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
  
 In den Beispielen dieses Abschnitts wird veranschaulicht, wie `PInvoke` verwendet werden kann.  `PInvoke` kann angepasstes Datenmarshalling vereinfachen, da Sie die Marshallinginformationen deklarativ in Attributen bereitstellen, anstatt prozeduralen Marshallingcode zu schreiben.  
  
> [!NOTE]
>  Die Marshallingbibliothek bietet eine alternative Möglichkeit, Daten auf optimierte Weise zwischen systemeigenen und verwalteten Umgebungen zu marshallen.  Weitere Informationen über die Marshallingbibliothek finden Sie unter [Übersicht über das Marshaling in C\+\+](../dotnet/overview-of-marshaling-in-cpp.md).  Die Marshallingbibliothek kann nur für Daten verwendet werden, nicht für Funktionen.  
  
## PInvoke und das DllImport\-Attribut  
 Im folgenden Beispiel wird die Verwendung von `PInvoke` in einem Visual C\+\+\-Programm veranschaulicht.  Die systemeigene Funktion puts ist in msvcrt.dll definiert.  Das DllImport\-Attribut wird für die Deklaration von puts verwendet.  
  
```  
// platform_invocation_services.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[DllImport("msvcrt", CharSet=CharSet::Ansi)]  
extern "C" int puts(String ^);  
  
int main() {  
   String ^ pStr = "Hello World!";  
   puts(pStr);  
}  
```  
  
 Das folgende Beispiel gleicht dem vorherigen Beispiel, verwendet jedoch IJW.  
  
```  
// platform_invocation_services_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#include <stdio.h>  
  
int main() {  
   String ^ pStr = "Hello World!";  
   char* pChars = (char*)Marshal::StringToHGlobalAnsi(pStr).ToPointer();   
   puts(pChars);  
  
   Marshal::FreeHGlobal((IntPtr)pChars);  
}  
```  
  
### Vorteile von IJW  
  
-   Es brauchen keine `DLLImport`\-Attributdeklarationen für die nicht verwalteten APIs geschrieben zu werden, die das Programm verwendet.  Schließen Sie einfach die Headerdatei ein, und stellen Sie eine Verknüpfung mit der Importbibliothek her.  
  
-   Der IJW\-Mechanismus ist etwas schneller \(die IJW\-Stubs müssen beispielsweise nicht die Notwendigkeit zum Fixieren oder Kopieren von Datenelementen prüfen, da dies explizit durch den Entwickler geschieht\).  
  
-   Leistungsaspekte werden eindeutig dargestellt.  In diesem Fall wird die Tatsache dargestellt, dass Sie eine Unicode\-Zeichenfolge in eine ANSI\-Zeichenfolge übersetzen und eine zugehörige Speicherbelegung und \-freigabe erfolgt.  In diesem Fall würde ein Entwickler, der den Code mit IJW schreibt, erkennen, dass das Aufrufen von `_putws` und die Verwendung von `PtrToStringChars` das Leistungsverhalten verbessern.  
  
-   Wenn Sie viele nicht verwaltete APIs mit denselben Daten aufrufen, ist es wesentlich effizienter, die Daten einmal zu marshallen und die gemarshallte Kopie zu übergeben, als die Daten jedes Mal neu zu marshallen.  
  
### Nachteile von IJW  
  
-   Marshalling muss explizit in Code statt durch Attribute \(die oft entsprechende Standards haben\) angegeben werden.  
  
-   Der Marshallingcode ist inline, wodurch er stärker in den Fluss der Anwendungslogik eindringt.  
  
-   Da die expliziten Marshalling\-APIs `IntPtr`\-Typen für 32\-Bit\- zu 64\-Bit\-Portierbarkeit zurückgeben, müssen Sie besondere `ToPointer`\-Aufrufe verwenden.  
  
 Die spezifische durch C\+\+ verfügbare Methode ist die effizientere explizite Methode, allerdings um den Preis erhöhter Komplexität.  
  
 Wenn in der Anwendung hauptsächlich nicht verwaltete Datentypen verwendet oder mehr nicht verwaltete APIs als .NET Framework\-APIs aufgerufen werden, sollten Sie das IJW\-Feature verwenden.  Bei gelegentlichen Aufrufen von nicht verwalteten APIs in einer überwiegend verwalteten Anwendung fällt die Wahl subtiler aus.  
  
## PInvoke mit Windows\-APIs  
 PInvoke eignet sich für aufrufende Funktionen in Windows.  
  
 In diesem Beispiel arbeitet ein Visual C\+\+\-Programm mit der MessageBox\-Funktion zusammen, die Teil der Win32\-API ist.  
  
```  
// platform_invocation_services_4.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
typedef void* HWND;  
[DllImport("user32", CharSet=CharSet::Ansi)]  
extern "C" int MessageBox(HWND hWnd, String ^ pText, String ^ pCaption, unsigned int uType);  
  
int main() {  
   String ^ pText = "Hello World! ";  
   String ^ pCaption = "PInvoke Test";  
   MessageBox(0, pText, pCaption, 0);  
}  
```  
  
 Bei der Ausgabe handelt es sich um ein Meldungsfeld mit dem Titel PInvoke Test, das den Text Hello World\! enthält.  
  
 Die Marshallinginformationen werden von PInvoke auch verwendet, um Funktionen in der DLL zu suchen.  Tatsächlich gibt es in user32.dll keine MessageBox\-Funktion, aber mit CharSet\=CharSet::Ansi kann PInvoke die ANSI\-Version, MessageBoxA, an Stelle der Unicode\-Version, MessageBoxW, verwenden.  Grundsätzlich sollten Sie Unicode\-Versionen nicht verwalteter APIs verwenden, weil dabei die aufwändige Übersetzung des systemeigenen Unicode\-Formats des .NET Framework\-Zeichenfolgenobjekts in ANSI entfällt.  
  
## Wann PInvoke nicht zu verwenden ist  
 Die Verwendung von PInvoke ist nicht für alle DLL\-Funktionen im C\-Format geeignet.  Angenommen, es gibt eine Funktion MakeSpecial in mylib.dll, die folgendermaßen deklariert ist.  
  
 `char * MakeSpecial(char * pszString);`  
  
 Zur Verwendung von PInvoke in einer Visual C\+\+\-Anwendung würde der Code in etwa folgendermaßen aussehen:  
  
 `[DllImport("mylib")]`  
  
 `extern "C" String * MakeSpecial([MarshalAs(UnmanagedType::LPStr)] String ^);`  
  
 Die Schwierigkeit dabei ist, dass wir den Speicher für die nicht verwaltete Zeichenfolge, die von MakeSpecial zurückgegeben wird, nicht löschen können.  Andere über PInvoke aufgerufene Funktionen geben einen Zeiger auf einen internen Puffer zurück, der nicht durch den Benutzer freigegeben werden muss.  In diesem Fall ist es naheliegend, das IJW\-Feature zu verwenden.  
  
## Beschränkungen von PInvoke  
 Sie dürfen nicht den gleichen exakten Zeiger von einer systemeigenen Funktion zurückgeben lassen, den Sie als Parameter verwendet haben.  Gibt eine systemeigene Funktion den Zeiger zurück, der mit PInvoke für sie gemarshallt wurde, kann dies Speicherschäden und Ausnahmen zur Folge haben.  
  
```  
__declspec(dllexport)  
char* fstringA(char* param) {  
   return param;  
}  
```  
  
 Im folgenden Beispiel wird dieses Problem veranschaulicht, und obwohl das Programm scheinbar eine korrekte Ausgabe liefert, kommt diese aus einem freigegebenen Speicherbereich.  
  
```  
// platform_invocation_services_5.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
#include <limits.h>  
  
ref struct MyPInvokeWrap {  
public:  
   [ DllImport("user32.dll", EntryPoint = "CharLower", CharSet = CharSet::Ansi) ]  
   static String^ CharLower([In, Out] String ^);  
};  
  
int main() {  
   String ^ strout = "AabCc";  
   Console::WriteLine(strout);  
   strout = MyPInvokeWrap::CharLower(strout);  
   Console::WriteLine(strout);  
}  
```  
  
## Marshalling von Argumenten  
 Zwischen verwalteten Typen und systemeigenen primitiven C\+\+\-Typen der gleichen Form ist bei Verwendung von `PInvoke` kein Marshalling erforderlich.  Zum Beispiel ist zwischen Int32 und int oder zwischen Double und double kein Marshalling erforderlich.  
  
 Aber Sie müssen Typen marshallen, die nicht das gleiche Formular aufweisen.  Dazu gehören Zeichen\-, Zeichenfolgen\- und Strukturtypen.  In der folgenden Tabelle werden die vom Marshaller für verschiedene Typen verwendeten Zuordnungen angezeigt:  
  
|wtypes.h|Visual C\+\+|Visual C\+\+ mit \/clr|Common Language Runtime|  
|--------------|------------------|----------------------------|-----------------------------|  
|HANDLE|void\*|void\*|IntPtr, UIntPtr|  
|BYTE|unsigned char|unsigned char|Byte|  
|SHORT|short|short|Int16|  
|WORD|unsigned short|unsigned short|UInt16|  
|INT|int|int|Int32|  
|UINT|unsigned int|unsigned int|UInt32|  
|LONG|long|long|Int32|  
|BOOL|long|bool|Boolean|  
|DWORD|unsigned long|unsigned long|UInt32|  
|ULONG|unsigned long|unsigned long|UInt32|  
|CHAR|char|char|Char|  
|LPCSTR|char\*|String ^ \[in\], StringBuilder ^ \[in, out\]|String ^ \[in\], StringBuilder ^ \[in, out\]|  
|LPCSTR|const char\*|String ^|Zeichenfolge|  
|LPWSTR|wchar\_t\*|String ^ \[in\], StringBuilder ^ \[in, out\]|String ^ \[in\], StringBuilder ^ \[in, out\]|  
|LPCWSTR|const wchar\_t \*|String ^|Zeichenfolge|  
|FLOAT|float|float|Single|  
|DOUBLE|double|double|Double|  
  
 Wenn die Adresse an eine nicht verwaltete Funktion übergeben wird, fixiert der Marshaller automatisch den auf dem Laufzeitheap belegten Speicherplatz.  Das Fixieren verhindert, dass der Garbage Collector den belegten Speicherblock während der Komprimierung verschiebt.  
  
 Im weiter oben gezeigten Beispiel gibt der CharSet\-Parameter von DllImport an, wie verwaltete Zeichenfolgen gemarshallt werden sollen; in diesem Fall sollen sie für die systemeigene Seite zu ANSI\-Zeichenfolgen gemarshallt werden.  
  
 Sie können Marshallinginformationen für einzelne Argumente einer systemeigenen Funktion mit dem MarshalAs\-Attribut angeben.  Es gibt mehrere Möglichkeiten, ein String \*\-Argument zu marshallen: BStr, ANSIBStr, TBStr, LPStr, LPWStr und LPTStr.  Der Standard ist LPStr.  
  
 In diesem Beispiel wird die Zeichenfolge als Doppelbyte\-Unicode\-Zeichenfolge, LPWStr, gemarshallt.  Die Ausgabe ist erste Buchstabe von "Hello World\!", weil das zweite Byte der gemarshallten Zeichenfolge NULL ist und "puts" dies als Markierung für das Zeichenfolgenende interpretiert.  
  
```  
// platform_invocation_services_3.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[DllImport("msvcrt", EntryPoint="puts")]  
extern "C" int puts([MarshalAs(UnmanagedType::LPWStr)] String ^);  
  
int main() {  
   String ^ pStr = "Hello World!";  
   puts(pStr);  
}  
```  
  
 Das MarshalAs\-Attribut befindet sich im System::Runtime::InteropServices\-Namespace.  Das Attribut kann mit anderen Datentypen, z. B. Arrays, verwendet werden.  
  
 Wie bereits in diesem Thema erwähnt, bietet die Marshallingbibliothek eine neue, optimierte Methode, Daten zwischen systemeigenen und verwalteten Umgebungen zu marshallen.  Weitere Informationen finden Sie unter [Übersicht über das Marshaling in C\+\+](../dotnet/overview-of-marshaling-in-cpp.md).  
  
## Überlegungen zur Leistung  
 Der Aufwand von PInvoke umfasst zwischen 10 und 30 x86\-Anweisungen pro Aufruf.  Über diesen festen Aufwand hinaus verursacht das Marshalling zusätzlichen Aufwand.  Zwischen blitfähigen Typen, die in verwaltetem und nicht verwaltetem Code gleich sind, entsteht kein Aufwand durch das Marshalling.  Z. B. kostet es keinen Aufwand, zwischen int und Int32 zu übersetzen.  
  
 Es verbessert die Leistung, mit möglichst wenigen PInvoke\-Aufrufen so viele Daten wie möglich zu marshallen, statt mehr Aufrufe zu verwenden, die jeweils wenige Daten marshallen.  
  
## Siehe auch  
 [Interoperabilität von systemeigenem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)