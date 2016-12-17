---
title: "Overview of Generics in Visual C++"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generics [C++], about generics"
  - "default initializers [C++]"
  - "type parameters [C++]"
  - "constructed types"
  - "type arguments [C++]"
  - "constructed types, open [C++]"
  - "open constructed types [C++]"
  - "constructed types, closed [C++]"
ms.assetid: 21f10637-0fce-4916-b925-6c86a126d3aa
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "mblome"
manager: "ghogen"
---
# Overview of Generics in Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Generika sind die parametrisierte Typen, die von der Common Language Runtime unterstützt werden.  Ein parametrisierter Typ ist ein Typ, der mit einem unbekannten Typparameter definiert ist, der angegeben wird, wenn das generische verwendet wird.  
  
## Warum Generika?  
 C\+\+\-Stützvorlagen und Vorlagen und die parametrisierte Generikaunterstützung gibt ein, um typisierte Auflistungsklassen zu erstellen.  Allerdings stellt Vorlagen Kompilierzeitparametrisierung.  Sie können eine Assembly verweisen, die eine Vorlagendefinition enthält und neue Spezialisierungen der Vorlage erstellen.  Sobald kompiliert, wird eine spezialisierte Vorlage wie jede andere Klasse oder Methode aus.  Im Gegensatz dazu wird Generika in MSIL als parametrisierter Typ ausgegeben, der von der Laufzeit bezeichnet wird, um einen parametrisierten Typ sein; Quellcode, der einer Assembly verweist, die ein generischer Typ enthält, kann Spezialisierungen des generischen Typs erstellen.  Weitere Informationen zum Vergleich von Visual C\+\+\-Vorlagen und \-Generika, finden Sie unter [Generics and Templates \(Visual C\+\+\)](../windows/generics-and-templates-visual-cpp.md).  
  
## Generische Funktionen und Typen  
 Klassentypen, solange sie verwaltete Typen sind, können generisch.  Ein Beispiel hierfür könnte eine `List`\-Klasse.  Der Typ eines Objekts in der Liste ist der Typparameter sein.  Wenn Sie eine `List`\-Klasse für viele verschiedene Objekttypen erfordern, bevor Generika können Sie `List`, das verwendet **System::Object** als Elementtyp verwendet.  Aber das wäre jedes ermöglichen in der Liste zu verwendenden Objekt \(einschließlich Objekte des falschen Typs.  Eine solche Liste wird eine nicht typisierte Auflistungsklasse aufgerufen.  Im günstigsten Fall können Sie den Typ zur Laufzeit überprüfen und eine Ausnahme auslösen.  Oder, Sie verwendet möglicherweise eine Vorlage, die die generische Qualität verlieren würde, die jeweils in eine Assembly kompiliert wurde.  Consumer Ihrer Assembly können eigene Spezialisierungen der Vorlage nicht erstellen.  Generika können, um typisierte Auflistungsklassen erstellen, lautet `List<int>` \(Lesen als "int Liste aus"\) und  `List<double>` \("Liste eines Doubles"\) die einen Kompilierzeitfehler generiert werden, wenn Sie versucht haben, einen Typ zu stellen, die die Auflistung nicht entworfen wurde, um in die typisierte Auflistung zu akzeptieren.  Darüber hinaus bleiben diese Typen generisch, wenn sie kompiliert sind.  
  
 Eine Beschreibung der Syntax der generischen Klassen wird in neuen Namespace A [Generic Classes \(C\+\+\/CLI\)](../windows/generic-classes-cpp-cli.md)`.` , <xref:System.Collections.Generic>, führt einen Satz parametrisierte Auflistungstypen einschließlich <xref:System.Collections.Generic.Dictionary`2>, <xref:System.Collections.Generic.List`1> und <xref:System.Collections.Generic.LinkedList`1> gefunden werden.  Weitere Informationen finden Sie unter [Generika in der .NET Framework\-Klassenbibliothek](../Topic/Generics%20in%20the%20.NET%20Framework%20Class%20Library%20\(C%23%20Programming%20Guide\).md).  
  
 Möglicherweise sind Instanz und statische Memberfunktionen, Delegaten und globale Funktionen auch generisch.  Generische Funktionen sind möglicherweise erforderlich, wenn die Parameter der Funktion von einem unbekannten Typ sind oder die Funktion selbst mit generischen Typen arbeiten muss.  In vielen Fällen, bei **System::Object** möglicherweise in der Vergangenheit als Parameter für einen unbekannten Objekttyp verwendet, wird ein generischer Typparameter kann stattdessen verwendet und können typsichereren Code.  Jeder Versuch, einen Typ zu übergeben, dass die Funktion nicht für entworfen wurde, könnte als Fehler zur Kompilierzeit wird.  Mit **System::Object** als Funktionsparameter, würde das unbeabsichtigte Übergabe eines Objekts, das die Funktion nicht vorgesehen ist, um zu begegnen, nicht und müssten Sie den unbekannten Objekttyp in einen bestimmten, umwandeln den Funktionsrumpf Variablen sowie die Möglichkeit eines InvalidCastException erkannt.  Mit einem generischen würde der Code, der versucht, ein Objekt zur Funktion zu übergeben, ein Typkonflikt verursachen, sodass der Funktionsrumpf garantiert, um den richtigen Typ aufweisen.  
  
 Die Vorteile betreffen die Auflistungsklassen zu, die auf Generika erstellt werden.  Auflistungsklassen in der Vergangenheit würden **System::Object** verwenden, um Elemente in einer Auflistung speichern.  Einfüge\- von Objekten eines Typs, dass die Auflistung nicht für entwickelt wurde, wurde nicht zur Kompilierzeit und häufig gekennzeichnet, nicht einmal wenn die Objekte eingefügt wurden.  Normalerweise würde ein Objekt zu einem anderen Typ umgewandelt, als im der Auflistung zugegriffen wurde.  Nur als die Umwandlung wurde, würde der unerwarteten Typs wurde.  Generika wird das Problem zur Kompilierzeit, indem sie jeden Code erkennen, der einen Typ ein, der nicht \(oder implizit\) konvertieren den Typparameter der generischen Auflistung entspricht.  
  
 Eine Beschreibung der Syntax, finden Sie unter [Generic Functions \(C\+\+\/CLI\)](../windows/generic-functions-cpp-cli.md).  
  
## Terminologie mit Generika verwendet  
  
##### Typparameter  
 Eine generische Deklaration enthält mindestens unbekannten Typen, die als *Typparameter* bezeichnet.  Typparameter werden einen Namen zugewiesen, der für den Typ im Text der generische Deklaration wird.  Der Typparameter wird als Typ innerhalb des Texts der generische Deklaration verwendet.  Die generische Deklaration für ListT \<\> enthält den Typparameter T.  
  
##### Typargumente  
 Das *Typargument* ist der Typ, der tatsächlich anstelle des Typparameters verwendet, wenn das generische für einen bestimmten Typ abgeleitet ist oder eingeben.  Beispielsweise ist `int` das Typargument in `List<int>`.  Werttypen und Handletypen sind nur die Typen, die als generisches Typargument zugelassen werden.  
  
##### Konstruierter Typ  
 Ein Typ, der von einem generischen Typ erstellt wird, wird als ein *konstruierter Typ*.  Ein Typ nicht vollständig angegeben, wie `List<T>` ist ein *offener konstruierter Typ*; ein vollständig angegebener Typ, wie `List<double>,` ist ein *geschlossener konstruierter Typ* oder *ein spezialisierter Typ*.  Geöffnete konstruierten Typen verwendet werden in der Definition anderer generischer Typen oder Methoden und nicht sind vollständig angegeben werden, bis das Einschließen generisch selbst angegeben ist.  So ist beispielsweise Folgendes ein Verwendung aus einem offenen generischen Typ als Basisklasse für ein generisches:  
  
 `// generics_overview.cpp`  
  
 `// compile with: /clr /c`  
  
 `generic <typename T>`  
  
 `ref class List {};`  
  
 `generic <typename T>`  
  
 `ref class Queue : public List<T> {};`  
  
##### Einschränkung  
 Eine Einschränkung ist eine Einschränkung für die Typen, die als Typparameter verwendet werden.  Beispielsweise kann eine bestimmte generische Klasse nur Klassen übernehmen, die von einer bestimmten Klasse erben, oder implementieren eine angegebene Schnittstelle.  Weitere Informationen finden Sie unter [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## Werttypen und Verweistypen  
 Handles Typen und Werttypen werden als Typargumente verwendet werden.  In generischen der Definition in der jeder Typ möglicherweise verwendet wird, ist die Syntax die von Referenztypen.  Beispielsweise wird der **\-\>**\-Operator verwendet, um auf Member des Typs des Typparameters zuzugreifen, ob der schließlich verwendete Typ ein Verweistyp oder ein Werttyp sein.  Wenn ein Werttyp als das Typargument verwendet wird, generiert die Laufzeit Code, der die Werttypen verwendet, ohne der Werttypen entfällt.  
  
 Wenn ein Referenztyp als generisches Typargument verwenden, verwenden Sie die Handlesyntax.  Wenn ein Werttyp als generisches Typargument verwenden, verwenden Sie den Namen des Typs direkt.  
  
 `// generics_overview_2.cpp`  
  
 `// compile with: /clr`  
  
 `generic <typename T>`  
  
 `ref class GenericType {};`  
  
 `ref class ReferenceType {};`  
  
 `value struct ValueType {};`  
  
 `int main() {`  
  
 `GenericType<ReferenceType^> x;`  
  
 `GenericType<ValueType> y;`  
  
 `}`  
  
## Typparameter  
 Typparameter in einer generischen Klasse werden wie andere Bezeichner behandelt.  Da der Typ nicht bekannt ist, dass es Beschränkungen bei ihrer Verwendung.  Beispielsweise können Sie Member nicht verwenden und Methoden des Typparameters Klasse, es sei denn, der Typparameter bezeichnet, diese Member zu unterstützen.  Das heißt, um einen Member durch den Typparameter zuzugreifen, müssen Sie den Typ hinzufügen, der den Member der Einschränkungsliste des Typparameters enthält.  
  
 `// generics_overview_3.cpp`  
  
 `// compile with: /clr`  
  
```  
interface class I {  
   void f1();  
   void f2();  
};  
  
ref struct R : public I {  
   virtual void f1() {}  
   virtual void f2() {}   
   virtual void f3() {}   
};  
  
generic <typename T>  
where T : I  
void f(T t) {  
   t->f1();  
   t->f2();  
   safe_cast<R^>(t)->f3();  
}  
  
int main() {  
   f(gcnew R());  
}  
```  
  
 Diese Einschränkungen gelten auch Operatoren an.  Ein zwangloser generischer Typparameter verwendet möglicherweise nicht die Operatoren `==` und `!=`, um zwei Instanzen des Typparameters zu vergleichen, falls der Typ nicht diese Operatoren unterstützt.  Diese Prüfungen sind für Generika, nicht aber für Vorlagen notwendig, da Generika möglicherweise zur Laufzeit mit einer beliebigen Klasse spezialisiert wird, die die Einschränkungen erfüllt, wenn diese zu spät, ist für die Verwendung ungültiger Member zu überprüfen.  
  
 Eine Standardinstanz des Typparameters wird erstellt werden, indem Sie den `()`\-Operator verwendet.  Beispiel:  
  
 `T t = T();`  
  
 wobei `T` ein Typparameter in einer generischen Klasse oder Methodendefinition ist, initialisiert die Variable den Standardwert.  Wenn `T` eine Verweisklasse ist, ist dies ein NULL\-Zeiger; wenn `T` eine Wertklasse ist, wird das Objekt auf Null initialisiert.  Dieses wird einen *Standardinitialisierer* aufgerufen.  
  
## Siehe auch  
 [Generics](../windows/generics-cpp-component-extensions.md)