---
title: CLR-Enumerationstyp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- scope, of CLR enum
- enum struct keyword [C++]
- enum class keyword [C++]
ms.assetid: 4541d952-97bb-4e35-a7f8-d14f5f6a6606
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ad82c1d867c511121cd024f2affd5df98b4642bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="clr-enum-type"></a>CLR-Enumerationstyp
Die Deklaration und das Verhalten von Enumerationen hat gegenüber Managed Extensions for C++ geändert für Visual C++.  
  
 Die Deklaration der Managed Extensions-Enumeration vorangestellt ist die `__value` Schlüsselwort. Hier die Idee ist das systemeigene Enumeration von der CLR-Enumeration zu unterscheiden, das von abgeleitet ist `System::ValueType`, während eine analoge Funktionalität bietet. Zum Beispiel:  
  
```  
__value enum e1 { fail, pass };  
public __value enum e2 : unsigned short  {   
   not_ok = 1024,   
   maybe, ok = 2048   
};  
```  
  
 Die neue Syntax löst das Problem der Unterscheidung systemeigener und CLR-Enumerationen, indem die Klasse Charakter der zweite Wert statt auf dessen Wert Typ Stämme hervorgehoben. Daher die `__value` Schlüsselwort wird verworfen, ersetzt durch das durch Leerzeichen getrennten Schlüsselwortpaar von `enum class`. Dies bietet eine gepaarte Schlüsselwort Symmetrie für die Deklarationen der Verweis, Wert und Schnittstellenklassen:  
  
```  
enum class ec;  
value class vc;  
ref class rc;  
interface class ic;  
```  
  
 Die Übersetzung des Enumerationspaars `e1` und `e2` in der neuen Syntax sieht wie folgt aus:  
  
```  
enum class e1 { fail, pass };  
public enum class e2 : unsigned short {   
   not_ok = 1024,  
   maybe, ok = 2048   
};  
```  
  
 Abgesehen von dieser kleinen syntaktischen Änderung wurde das Verhalten der CLR-Enumerationstyp auf vielfältige Weise geändert:  
  
-   Eine Vorwärtsdeklaration einer CLR-Enumeration wird nicht mehr unterstützt. Keine Zuordnung ist vorhanden. Es ist einfach als ein Fehler während der Kompilierung gekennzeichnet.  
  
```  
__value enum status; // Managed Extensions: ok  
enum class status;   // new syntax: error  
```  
  
-   Die Auflösung von funktionsüberladungen zwischen den integrierten arithmetischen Typen und die `Object` Klassenhierarchie wurde storniert, zwischen den beiden Sprachversionen! Als Nebeneffekt werden die CLR-Enumerationen nicht mehr implizit in arithmetische Typen konvertiert.  
  
-   In der neuen Syntax verwaltet eine CLR-Enumeration einen eigenen Bereich, der nicht der Fall in Managed Extensions ist. Zuvor waren die Enumeratoren innerhalb des enthaltenen Bereichs der Enumeration sichtbar. Jetzt sind die Enumeratoren innerhalb des Bereichs der Enumeration gekapselt.  
  
## <a name="clr-enums-are-a-kind-of-object"></a>CLR-Enumerationen sind eine Art von Objekt  
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
  
 Für den systemeigenen C++-Programmierer der natürlichen beantworten, auf die Frage, welche Instanz der überladenen `f()` wird aufgerufen, wird der `f(int)`. Eine Enumeration ist eine symbolische ganzzahlige Konstante und er beteiligt ist, in der standard ganzzahligen Erweiterungen, die in diesem Fall Vorrang.  Und in Managed Extensions war dies tatsächlich der Instanz in die der Aufruf aufgelöst wird. Dies darauf zurückzuführen, dass eine Anzahl von überraschungen - nicht verwendet wurde, in einem systemeigenen C++ Frame -, sondern sie für die Interaktion mit dem vorhandenen BCL (Base Class Library)-Framework, in dem ein `Enum` ist eine indirekt von abgeleitete Klasse `Object`. In Visual C++ Language Design, die die Instanz von `f()` aufgerufen wird, die der `f(Object^)`.  
  
 Die Möglichkeit, die Visual C++ ausgewählt hat, um dies zu erzwingen werden keine implizite Konvertierungen zwischen einer CLR-Enumerationstyp und arithmetischen Typen unterstützt. Dies bedeutet, dass jede Zuweisung eines Objekts von einem CLR-Enumerationstyp auf einen arithmetischen Typ eine explizite Umwandlung erfordern. Also z. B. erhalten.  
  
```  
void f( int );  
```  
  
 als eine Methode nicht überladen in Managed Extensions wird der Aufruf  
  
```  
f( rslt ); // ok: Managed Extensions; error: new syntax  
```  
  
 Ok, und der Wert enthaltenen `rslt` implizit in einen ganzzahligen Wert konvertiert wird. In Visual C++ kann dieser Aufruf nicht kompiliert. Um übersetzen ordnungsgemäß zu können, müssen wir einen Konvertierungsoperator einfügen:  
  
```  
f( safe_cast<int>( rslt )); // ok: new syntax  
```  
  
## <a name="the-scope-of-the-clr-enum-type"></a>Der Bereich der CLR-Enumerationstyp  
 Eine der Änderungen zwischen den Programmiersprachen C und C++ war das Hinzufügen der Bereich innerhalb der Struktur-Funktion in C++. Eine Struktur ist in C nur ein Datenaggregat ohne Unterstützung für eine Schnittstelle oder ein zugeordneter Bereich. Dies war eine ziemlich radikale Änderung zum Zeitpunkt und einen Streitpunkt für viele neue C++-Benutzer, die der Programmiersprache C stammt. Die Beziehung zwischen der systemeigenen und der CLR-Enumeration entspricht.  
  
 In Managed Extensions wurde versucht, schwach eingefügte Namen für die Enumeratoren einer CLR-Enumeration zu definieren, um das Fehlen des Bereichs in das systemeigene Enumeration zu simulieren. Dies nicht erfolgreich verlaufen sind. Das Problem ist, dass dies bewirkt, die Enumeratoren in den globalen Namespace, die schwer dass zu verwalten Namenskonflikte Überlauf. In der neuen Syntax haben wir für die andere CLR-Sprachen bei der Unterstützung von Bereichen innerhalb der CLR-Enumeration angepasst.  
  
 Dies bedeutet, dass nicht qualifizierte Verwendung eines Enumerators einer CLR-Enumeration nicht durch die neue Syntax erkannt werden. Sehen wir uns ein praktisches Beispiel.  
  
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
  
      // here are the problems...  
      optionList->Add(S"?", __box(OPTION_USAGE)); // (1)  
      optionList->Add(S"help", __box(OPTION_USAGE)); // (2)  
  
      itagList = new ListDictionary;  
      itagList->Add(S"returns",   
         __box(XDC0004_WRN_XML_LOAD_FAILURE)); // (3)  
   }  
};  
```  
  
 Jeder der drei nicht qualifizierten Namen Enumerator verwendet (`(1)`, `(2)`, und `(3)`) in der Übersetzung in die neue Syntax in der Reihenfolge für den Quellcode zu kompilieren qualifiziert werden müssen. Hier ist eine ordnungsgemäße Übersetzung von den ursprünglichen Quellcode:  
  
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
  
 Dies ändert die Strategie beim Anwendungsentwurf zwischen systemeigenen und eine CLR-Enumeration. Mit einer CLR-Enumeration, der einen zugehörigen Gültigkeitsbereich in Visual C++ verwaltet wird ist es weder nötig noch effektiv, die Deklaration der Enumeration innerhalb einer Klasse zu kapseln. Diese Ausdrucksweise hat sich die zum Ereigniszeitpunkt Cfront 2.0 innerhalb Bell Laboratories auch um die globalen Namen Verunreinigung Problem zu beheben.  
  
 In der ursprünglichen Betaversion der neuen Iostream-Bibliothek von Jerry Schwarz Bell Laboratories, nicht gekapselt alle für die Bibliothek und die allgemeinen Enumeratoren, z. B. definierten zugehörigen Enumerationen `read`, `write`, `append`usw. , versucht es nahezu unmöglich, damit Benutzer ihren vorhandenen Code zu kompilieren. Eine Lösung hätte, wie z. B. die Namen mangle `io_read`, `io_write`usw. Eine zweite Lösung, die Sprachpakete zu ändern, indem Enum Gültigkeitsbereich hinzugefügt hätte, dies war jedoch nicht durchführbar zu dem Zeitpunkt. Die mittlere Lösung bestand darin Kapseln der Enumeration innerhalb der Klasse oder Klassenhierarchie, in dem Auffüllen der Tagname und die Enumeratoren der Enumeration der Gültigkeitsbereich der einschließenden Klasse.) Platzieren von Enumerationen innerhalb von Klassen, mindestens ursprünglich war also nicht philosophischen, aber eine praktische Reaktion auf das Problem globalen Namensbereich Beschädigung.  
  
 Mit der Visual C++-Enumeration ist nicht mehr nennenswerten Vorteil Kapseln einer Enumeration innerhalb einer Klasse. Tatsächlich ist bei Betrachtung der `System` Namespaces können Sie sehen, Enumerationen, Klassen und Schnittstellen, die alle in einem Deklarationsabschnitt einen.  
  
## <a name="see-also"></a>Siehe auch  
 [Werttypen und ihr Verhalten (C + c++ / CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Enumerationsklasse](../windows/enum-class-cpp-component-extensions.md)