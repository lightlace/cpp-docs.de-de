---
title: "Gewusst wie: Einen STL/CLR-Container einer Assembly verf&#252;gbar machen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STL/CLR-Container [STL/CLR]"
  - "STL/CLR, cross-assembly-Probleme"
ms.assetid: 87efb41b-3db3-4498-a2e7-f3ef8a99f04d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Gewusst wie: Einen STL/CLR-Container einer Assembly verf&#252;gbar machen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

STL\/CLR\-Container wie `list` und `map` werden als Vorlagenverweisklassen implementiert.  Da C\+\+\-Vorlagen zur Kompilierzeit instanziiert werden, zwei Vorlagenklassen, die genau die gleiche Signatur haben, jedoch, in unterschiedlichen Assemblys sind tatsächlich verschiedene Typen sind.  Dies bedeutet, dass Vorlagenklassen nicht über Assemblygrenzen verwendet werden können.  
  
 So assemblyübergreifende Freigabe ist, STL\/CLR\-Containerwerkzeug die generische <xref:System.Collections.Generic.ICollection`1>\- Schnittstelle.  Mithilfe dieser generische Schnittstelle verwenden, können alle Sprachen, einschließlich Generika, die C\+\+, C\# und Visual Basic unterstützen, auf STL\/CLR\-Container zugreifen.  
  
 Dieses Thema veranschaulicht, wie die Elemente verschiedener STL\/CLR\-Container anzeigt, die in eine C\+\+\-Datei Assembly mit dem Namen `StlClrClassLibrary` geschrieben werden.  Es werden zwei Assemblys an, um auf `StlClrClassLibrary` zuzugreifen.  Die erste Assembly wird in C\+\+ und in die zweite in C\# geschrieben.  
  
 Wenn beide Assemblys in C\+\+ geschrieben werden, können Sie auf die generische Schnittstelle eines Containers zugreifen, indem Sie seine `generic_container`\-Typedef verwenden.  Wenn Sie einen Container Typ `cliext::vector<int>` verfügen, dessen generische Schnittstelle ist: `cliext::vector<int>::generic_container`.  Ebenso können Sie keinen Iterator über die generischen Schnittstelle abrufen, indem Sie die `generic_iterator` sind, wie in verwenden: `cliext::vector<int>::generic_iterator`.  
  
 Da diese Typdefinitionen in C\+\+\-Headerdateien deklariert werden, können Assemblys, die in anderen Sprachen geschrieben werden, nicht verwenden.  Daher auf die generische Schnittstelle für `cliext::vector<int>` in C\# oder in einer anderen .NET\-Sprache zugreifen, verwenden Sie `System.Collections.Generic.ICollection<int>`.  Um über dieser Auflistung durchlaufen, verwenden Sie eine `foreach` \- Schleife.  
  
 Die folgende Tabelle zeigt die generische Schnittstelle, auf die jeder STL\/CLR\-Container implementiert:  
  
|STL\/CLR\-Container|Generische Schnittstelle|  
|-------------------------|------------------------------|  
|dequeT \<\>|ICollectionT \<\>|  
|hash\_mapK \<, V\>|IDictionaryK \<, V\>|  
|hash\_multimapK \<, V\>|IDictionaryK \<, V\>|  
|hash\_multisetT \<\>|ICollectionT \<\>|  
|hash\_setT \<\>|ICollectionT \<\>|  
|listT \<\>|ICollectionT \<\>|  
|mapK \<, V\>|IDictionaryK \<, V\>|  
|multimapK \<, V\>|IDictionaryK \<, V\>|  
|multisetT \<\>|ICollectionT \<\>|  
|Pflasterstein \<\>|ICollectionT \<\>|  
|vectorT \<\>|ICollectionT \<\>|  
  
> [!NOTE]
>  Da `queue`, `priority_queue` und `stack` keine Iteratoren Container unterstützen, implementieren sie nicht generische Schnittstellen und können nicht zugreifen assemblyübergreifendes sein.  
  
## Beispiel 1  
  
### **Beschreibung**  
 In diesem Beispiel deklarieren wir eine C\+\+\-Klasse, die private STL\/CLR\-Memberdaten enthält.  Wir deklarieren dann öffentliche Methoden zum Zugriff auf die Privatsammlungen der Klasse.  Wir führen sie auf zwei verschiedene Methoden, eine für C\+\+\-Clients und eine andere für .NET\-Clients.  
  
### Code  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## Beispiel 2  
  
### **Beschreibung**  
 In diesem Beispiel implementieren wir die Klasse, die in diesem Beispiel 1. deklariert wird.  Damit Clients verwenden diese Klassenbibliothek, verwenden wir das Manifesttool **mt.exe**, um die Manifestdatei in die DLL einzubetten.  Ausführliche Informationen finden Sie in den Codekommentaren.  
  
 Weitere Informationen zum Manifesttool und die parallelen Assemblys, finden Sie unter [Erstellen von isolierten Anwendungen und parallelen Assemblys \(C\/C\+\+\)](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md).  
  
### Code  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## Beispiel 3  
  
### **Beschreibung**  
 In diesem Beispiel erstellen wir Client eine C\+\+\-Headerdatei erstellt, der die Klassenbibliothek verwendet, die in Beispielen 1 und 2. erstellt wird.  Dieser Client verwendet die `generic_container`\-Typdefinitionen der STL\/CLR\-Container, um über den Containern zu durchlaufen und deren Inhalt anzuzeigen.  
  
### Code  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
### Ausgabe  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
## Beispiel 4  
  
### **Beschreibung**  
 In diesem Beispiel erstellen wir ein C\#\-Client erstellt, der die Klassenbibliothek verwendet, die in Beispielen 1 und 2. erstellt wird.  Dieser Client verwendet die Methoden <xref:System.Collections.Generic.ICollection`1> \/CLR\-Container der STL, um über den Containern zu durchlaufen und deren Inhalt anzuzeigen.  
  
### Code  
  
```  
// CsConsoleApp.cs  
// compile with: /r:Microsoft.VisualC.STLCLR.dll /r:StlClrClassLibrary.dll /r:System.dll  
  
using System;  
using System.Collections.Generic;  
using StlClrClassLibrary;  
using cliext;  
  
namespace CsConsoleApp  
{  
    class Program  
    {  
        static int Main(string[] args)  
        {  
            StlClrClass theClass = new StlClrClass();  
  
            Console.WriteLine("cliext::deque contents:");  
            ICollection<char> iCollChar = theClass.GetDequeCs();  
            foreach (char c in iCollChar)  
            {  
                Console.WriteLine(c);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::list contents:");  
            ICollection<float> iCollFloat = theClass.GetListCs();  
            foreach (float f in iCollFloat)  
            {  
                Console.WriteLine(f);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::map contents:");  
            IDictionary<int, string> iDict = theClass.GetMapCs();  
            foreach (KeyValuePair<int, string> kvp in iDict)  
            {  
                Console.WriteLine("{0} {1}", kvp.Key, kvp.Value);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::set contents:");  
            ICollection<double> iCollDouble = theClass.GetSetCs();  
            foreach (double d in iCollDouble)  
            {  
                Console.WriteLine(d);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::vector contents:");  
            ICollection<int> iCollInt = theClass.GetVectorCs();  
            foreach (int i in iCollInt)  
            {  
                Console.WriteLine(i);  
            }  
            Console.WriteLine();  
  
            return 0;  
        }  
    }  
}  
```  
  
### Ausgabe  
  
```  
cliext::deque contents:  
a  
b  
  
cliext::list contents:  
3.14159  
2.71828  
  
cliext::map contents:  
0 Hello  
1 World  
  
cliext::set contents:  
2.71828  
3.14159  
  
cliext::vector contents:  
10  
20  
```  
  
## Siehe auch  
 [STL\/CLR\-Bibliothek](../dotnet/stl-clr-library-reference.md)