---
title: "CLR-Enumerationstyp | Microsoft Docs"
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
  - "enum class-Schlüsselwort [C++]"
  - "enum struct-Schlüsselwort [C++]"
  - "Gültigkeitsbereich, Von CLR enum"
ms.assetid: 4541d952-97bb-4e35-a7f8-d14f5f6a6606
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# CLR-Enumerationstyp
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Deklaration und das Verhalten von Enumerationen hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions for C\+\+ geändert.  
  
 Der Deklaration der Managed Extensions\-Enumeration wird das `__value`\-Schlüsselwort vorangestellt.  Die allgemeine Vorgehensweise besteht darin, die systemeigene Enumeration von der CLR\-Enumeration zu unterscheiden, die von `System::ValueType` abgeleitet ist, jedoch eine analoge Funktionalität bietet.  Beispiel:  
  
```  
__value enum e1 { fail, pass };  
public __value enum e2 : unsigned short  {   
   not_ok = 1024,   
   maybe, ok = 2048   
};  
```  
  
 Die neue Syntax löst das Problem der Unterscheidung systemeigener Enumerationen von CLR\-Enumerationen, indem der Klassencharakter der CLR\-Enumerationen anstelle der zugrunde liegenden Werttypen betont wird.  Das heißt, das `__value`\-Schlüsselwort wird verworfen und durch das durch Leerzeichen getrennte Schlüsselwortpaar `enum class` ersetzt.  Damit werden symmetrische Schlüsselwortpaare für die Deklarationen der Verweis\-, Wert\- und Schnittstellenklassen geschaffen:  
  
```  
enum class ec;  
value class vc;  
ref class rc;  
interface class ic;  
```  
  
 Die Übersetzung des Enumerationspaars `e1` und `e2` in der neuen Syntax sieht folgendermaßen aus:  
  
```  
enum class e1 { fail, pass };  
public enum class e2 : unsigned short {   
   not_ok = 1024,  
   maybe, ok = 2048   
};  
```  
  
 Abgesehen von dieser kleinen syntaktischen Änderung hat sich eine Reihe von Änderungen beim Verhalten des CLR\-Enumerationstyps ergeben:  
  
-   Die Vorwärtsdeklaration einer CLR\-Enumeration wird nicht mehr unterstützt.  Es gibt keine Zuordnung.  Sie wird lediglich als Kompilierzeitfehler gekennzeichnet.  
  
```  
__value enum status; // Managed Extensions: ok  
enum class status;   // new syntax: error  
```  
  
-   Die Überladungsauflösung zwischen den integrierten arithmetischen Typen und der `Object`\-Klassenhierarchie wurde zwischen den beiden Sprachversionen umgekehrt.  Als Nebeneffekt werden CLR\-Enumerationen nicht mehr implizit in arithmetische Typen konvertiert.  
  
-   In der neuen Syntax verwaltet eine CLR\-Enumeration ihren eigenen Gültigkeitsbereich, was bei Managed Extensions nicht der Fall ist.  Vorher waren die Enumeratoren im enthaltenen Gültigkeitsbereich der Enumeration sichtbar.  Jetzt sind die Enumeratoren im Gültigkeitsbereich der Enumeration gekapselt.  
  
## CLR\-Enumerationen sind eine Art Objekt  
 Betrachten Sie das folgende Codefragment:  
  
```  
__value enum status { fail, pass };  
  
void f( Object* ){ Console::WriteLine("f(Object)\n"); }  
void f( int ){ Console::WriteLine("f(int)\n"); }  
  
int main()  
{  
   status rslt = fail;  
  
   f( rslt ); // which f is invoked?  
}  
```  
  
 Ein erfahrener C\+\+\-Programmierer weiß selbstverständlich, welche Instanz der überladenen Funktion `f()` aufgerufen wird: `f(int)`.  Eine Enumeration ist eine symbolische ganzzahlige Konstante, die an den standardmäßigen ganzzahligen Erweiterungen beteiligt ist, die in diesem Fall Vorrang haben.  In Managed Extensions ist dies auch tatsächlich die Instanz, für die der Aufruf aufgelöst wird.  Diese Auflösung hat jedoch zu unerwarteten Ergebnissen geführt, wenn die Enumeration nicht in der systemeigenen C\+\+\-Einstellung verwendet wurde, sondern mit dem vorhandenen BCL \(Base Class Library, Basisklassenbibliothek\)\-Framework interagieren sollte, in dem eine `Enum` eine indirekt von `Object` abgeleitete Klasse darstellt.  Im [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)]\-Sprachdesign entspricht die aufgerufene Instanz von `f()` der von `f(Object^)`.  
  
 [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] hat dies auf die Art und Weise erzwungen, dass keine impliziten Konvertierungen zwischen einem CLR\-Enumerationstyp und den arithmetischen Typen unterstützt werden.  Das heißt, dass eine beliebige Zuweisung eines Objekts eines CLR\-Enumerationstyps zu einem arithmetischen Typ eine explizite Umwandlung erfordert.  Wenn also z. B.  
  
```  
void f( int );  
```  
  
 eine nicht überladene Methode ist, ist in Managed Extensions der Aufruf  
  
```  
f( rslt ); // ok: Managed Extensions; error: new syntax  
```  
  
 korrekt, und der in `rslt` enthaltene Wert wird implizit in einen ganzzahligen Wert konvertiert.  In [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] wird dieser Aufruf nicht kompiliert.  Um ihn ordnungsgemäß zu übersetzen, muss ein Konvertierungsoperator eingefügt werden:  
  
```  
f( safe_cast<int>( rslt )); // ok: new syntax  
```  
  
## Der Gültigkeitsbereich des CLR\-Enumerationstyps  
 Eine der Änderungen zwischen den Programmiersprachen C und C\+\+ ist die, dass in C\+\+ innerhalb der Strukturfunktion ein Gültigkeitsbereich hinzugefügt wurde.  In C stellt eine Struktur lediglich ein Datenaggregat ohne Unterstützung einer Schnittstelle oder eines dazugehörigen Gültigkeitsbereichs dar.  Diese grundlegende Änderung, die C\+\+ mit sich brachte, stellte für viele C\+\+\-Benutzer, die vorher mit der Programmiersprache C gearbeitet hatten, einen Streitpunkt dar.  Die Beziehung zwischen der systemeigenen und der CLR\-Enumeration ist analog.  
  
 In Managed Extensions wurde versucht, schwach eingefügte Namen für die Enumeratoren einer CLR\-Enumeration zu definieren, um das Fehlen eines Gültigkeitsbereichs innerhalb der systemeigenen Enumeration zu simulieren.  Dies erwies sich jedoch als nicht erfolgreich.  Das Problem liegt darin, dass auf diese Weise die Enumeratoren in den globalen Namespace gelangen und Namenskonflikte auslösen können, die schwer zu beheben sind.  In der neuen Syntax wurde daher die Konformität mit den anderen CLR\-Programmiersprachen bei der Unterstützung von Gültigkeitsbereichen innerhalb der CLR\-Enumeration sichergestellt.  
  
 Dadurch wird eine nicht qualifizierte Verwendung eines Enumerators einer CLR\-Enumeration in der neuen Syntax nicht erkannt.  Betrachten Sie das folgende praxisnahe Beispiel.  
  
```  
// Managed Extensions supporting weak injection  
__gc class XDCMake {  
public:  
   __value enum _recognizerEnum {   
      UNDEFINED,  
      OPTION_USAGE,   
      XDC0001_ERR_PATH_DOES_NOT_EXIST = 1,  
      XDC0002_ERR_CANNOT_WRITE_TO = 2,  
      XDC0003_ERR_INCLUDE_TAGS_NOT_SUPPORTED = 3,  
      XDC0004_WRN_XML_LOAD_FAILURE = 4,  
      XDC0006_WRN_NONEXISTENT_FILES = 6,  
   };  
  
   ListDictionary* optionList;  
   ListDictionary* itagList;  
  
   XDCMake() {  
      optionList = new ListDictionary;  
  
      // here are the problems …  
      optionList->Add(S"?", __box(OPTION_USAGE)); // (1)  
      optionList->Add(S"help", __box(OPTION_USAGE)); // (2)  
  
      itagList = new ListDictionary;  
      itagList->Add(S"returns",   
         __box(XDC0004_WRN_XML_LOAD_FAILURE)); // (3)  
   }  
};  
```  
  
 Jede der drei nicht qualifizierten Verwendungen der Enumeratorennamen \(`(1)`, `(2)` und `(3)`\) muss bei der Übersetzung in die neue Syntax qualifiziert werden, damit der Quellcode kompiliert werden kann.  Hier sehen Sie eine richtige Übersetzung des ursprünglichen Quellcodes:  
  
```  
ref class XDCMake {  
public:  
   enum class _recognizerEnum {  
      UNDEFINED, OPTION_USAGE,   
      XDC0001_ERR_PATH_DOES_NOT_EXIST = 1,  
      XDC0002_ERR_CANNOT_WRITE_TO = 2,  
      XDC0003_ERR_INCLUDE_TAGS_NOT_SUPPORTED = 3,  
      XDC0004_WRN_XML_LOAD_FAILURE = 4,  
      XDC0006_WRN_NONEXISTENT_FILES = 6  
   };  
  
   ListDictionary^ optionList;  
   ListDictionary^ itagList;  
  
   XDCMake() {  
      optionList = gcnew ListDictionary;  
      optionList->Add("?",_recognizerEnum::OPTION_USAGE); // (1)  
      optionList->Add("help",_recognizerEnum::OPTION_USAGE); //(2)  
      itagList = gcnew ListDictionary;  
      itagList->Add( "returns",   
         _recognizerEnum::XDC0004_WRN_XML_LOAD_FAILURE); //(3)  
   }  
};  
```  
  
 Dadurch ändert sich die Entwurfsstrategie zwischen einer systemeigenen Enumeration und einer CLR\-Enumeration.  Wenn eine CLR\-Enumeration einen zugehörigen Gültigkeitsbereich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] verwaltet, ist es nicht notwendig und auch nicht effektiv, die Deklaration der Enumeration innerhalb einer Klasse zu kapseln.  Diese Ausdrucksweise wurde bei Bell Laboratories im Zeitraum der Marktpräsenz von cfront 2.0 verbessert, auch, um das Problem der globalen Namensverunreinigung zu beheben.  
  
 In der ursprünglichen Betaversion der neuen iostream\-Bibliothek von Jerry Schwarz \(Bell Laboratories\) wurden nicht alle für die Bibliothek definierten zugehörigen Enumerationen gekapselt, und die allgemeinen Enumeratoren, z. B. `read`, `write`, `append` usw. machten es Benutzern nahezu unmöglich, ihren vorhandenen Code zu kompilieren.  Eine Lösung wäre, die Namen, wie `io_read`, `io_write`, zu ergänzen. gewesen sein usw. Die zweite Lösung wäre, die das Ändern der Sprache sein, mit Bereich zu einer Enumeration gewesen, was diese war zu der Zeit allerdings nicht durchführbar gewesen.  Der Mittelweg war das Kapseln der Enumeration innerhalb einer Klasse oder Klassenhierarchie, wobei sowohl der Tagname als auch die Enumeratoren der Enumeration den einschließenden Gültigkeitsbereich der Klasse auffüllen. Das Platzieren von Enumerationen innerhalb von Klassen hatte also zumindest ursprünglich keinen philosophischen Hintergrund, sondern war eine praktische Reaktion auf das Problem der globalen Namespaceverunreinigung.  
  
 Durch die [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)]\-Enumeration bringt das Kapseln einer Enumeration innerhalb einer Klasse keinen nennenswerten Vorteil mehr mit sich.  Wenn Sie einen Blick auf die `System`\-Namespaces werfen, können Sie feststellen, dass alle Enumerationen, Klassen und Schnittstellen im selben Deklarationsabschnitt enthalten sind.  
  
## Siehe auch  
 [Werttypen und ihr Verhalten \(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [enum class](../windows/enum-class-cpp-component-extensions.md)