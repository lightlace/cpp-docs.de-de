---
title: "Vorgehensweise: verfügbar zu machen einen STL/CLR-Container aus einer Assembly | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, cross-assembly issues
ms.assetid: 87efb41b-3db3-4498-a2e7-f3ef8a99f04d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 84505edf0877a5ae20d28906dde7f4c709574034
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-expose-an-stlclr-container-from-an-assembly"></a>Gewusst wie: Einen STL/CLR-Container einer Assembly verfügbar machen
STL/CLR-Container, z. B. `list` und `map` werden als vorlagenverweisklassen implementiert. Da C++-Vorlagen zum Zeitpunkt der Kompilierung nicht instanziiert werden, sind zwei Vorlagenklassen, die genau die gleiche Signatur haben, aber in verschiedenen Assemblys sind tatsächlich verschiedene Typen. Dies bedeutet, dass Vorlagenklassen Assembly hinweg verwendet werden können.  
  
 Um assemblyübergreifenden Freigabe zu ermöglichen, STL/CLR-Container implementieren die generische Schnittstelle <xref:System.Collections.Generic.ICollection%601>. Diese generischen Schnittstelle können, alle Sprachen, die Generika, z. B. C++, c# und Visual Basic, unterstützen STL/CLR-Container zugreifen.  
  
 Dieses Thema veranschaulicht, wie die Elemente von mehreren STL/CLR-Container aus einer C++-Assembly mit dem Namen angezeigt `StlClrClassLibrary`. Wir zeigen zwei Assemblys den Zugriff auf `StlClrClassLibrary`. Die erste Assembly wird in C++ und der zweite in c# geschrieben.  
  
 Wenn beide Assemblys in C++ geschrieben sind, können Sie die generische Schnittstelle eines Containers zugreifen, mithilfe dessen `generic_container` Typedef. Angenommen, Sie haben einen Container des Typs `cliext::vector<int>`, dann ist die generische Schnittstelle: `cliext::vector<int>::generic_container`. Auf ähnliche Weise erhalten Sie einen Iterator über die generische Schnittstelle mit dem `generic_iterator` Typedef verwendet werden, wie im: `cliext::vector<int>::generic_iterator`.  
  
 Seit dieser Typdefinitionen im C++-Headerdateien deklariert werden, können keine Assemblys, die in anderen Sprachen geschrieben werden. Aus diesem Grund die generische Schnittstelle für den Zugriff auf `cliext::vector<int>` in c# oder einer beliebigen anderen Sprache von .NET verwenden `System.Collections.Generic.ICollection<int>`. Um diese Auflistung durchlaufen, verwenden eine `foreach` Schleife.  
  
 Die folgende Tabelle enthält die generische Schnittstelle, die jeder STL/CLR-Container implementiert:  
  
|STL/CLR-container|Generische Schnittstelle|  
|------------------------|-----------------------|  
|Deque < T\>|ICollection < T\>|  
|hash_map-Element < K, V >|IDictionary < K, V >|  
|hash_multimap-Element < K, V >|IDictionary < K, V >|  
|hash_multiset-Element < T\>|ICollection < T\>|  
|Hash_set < T\>|ICollection < T\>|  
|Liste < T\>|ICollection < T\>|  
|Zuordnen von < K, V >|IDictionary < K, V >|  
|Multimap < K, V >|IDictionary < K, V >|  
|Multiset < T\>|ICollection < T\>|  
|Legen Sie < T\>|ICollection < T\>|  
|Vector < T\>|ICollection < T\>|  
  
> [!NOTE]
>  Da die `queue`, `priority_queue`, und `stack` Container unterstützen keine Iteratoren, sie möchten nicht generische Schnittstellen implementieren und können nicht assemblyübergreifenden zugegriffen werden.  
  
## <a name="example-1"></a>Beispiel 1  
  
### <a name="description"></a>Beschreibung  
 In diesem Beispiel deklarieren wir eine C++-Klasse, die private STL/CLR-Elementdaten enthält. Wir deklarieren dann öffentliche Methoden Zugriff auf die privaten Auflistungen der-Klasse. Wir machen es zwei Möglichkeiten, eine für C++-Clients und eine für andere Clients .NET.  
  
### <a name="code"></a>Code  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## <a name="example-2"></a>Beispiel 2  
  
### <a name="description"></a>Beschreibung  
 In diesem Beispiel implementieren wir die Klasse, die in Beispiel 1 deklariert. Damit Clients diese Klassenbibliothek verwenden, verwenden wir die Manifesttool **mt.exe** die Manifestdatei in die DLL einbetten. Einzelheiten finden Sie in den Kommentaren im Code.  
  
 Weitere Informationen auf die Seite-an-Seite-Assemblys und Manifesttool finden Sie unter [Erstellen von C/C++-isolierte Anwendungen und Side-by-Side Assemblys](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md).  
  
### <a name="code"></a>Code  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## <a name="example-3"></a>Beispiel 3  
  
### <a name="description"></a>Beschreibung  
 In diesem Beispiel erstellen wir einen C++-Client, der die Klassenbibliothek erstellt haben, in den Beispielen 1 und 2 verwendet. Dieser Client verwendet die `generic_container` Typdefinitionen der STL/CLR-Container, die Container durchlaufen und um ihren Inhalt anzuzeigen.  
  
### <a name="code"></a>Code  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
### <a name="output"></a>Ausgabe  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
## <a name="example-4"></a>Beispiel 4  
  
### <a name="description"></a>Beschreibung  
 In diesem Beispiel erstellen wir einen c#-Client, der die Klassenbibliothek erstellt haben, in den Beispielen 1 und 2 verwendet. Dieser Client verwendet die <xref:System.Collections.Generic.ICollection%601> Methoden der STL/CLR-Container, die Container durchlaufen und um ihren Inhalt anzuzeigen.  
  
### <a name="code"></a>Code  
  
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
  
### <a name="output"></a>Ausgabe  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)