---
title: "Vorgehensweise: Bereitstellen von Arbeitsfunktionen für die Call- und Transformer-Klassen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- call class, example
- using the transformer class [Concurrency Runtime]
- using the call class [Concurrency Runtime]
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: aafa676a1c6b885b303634c4fc31bcbfc1c6f0ab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-provide-work-functions-to-the-call-and-transformer-classes"></a>Gewusst wie: Bereitstellen von Arbeitsfunktionen für die call- und transformer-Klassen
In diesem Thema werden verschiedene Möglichkeiten zum Bereitstellen von Arbeitsfunktionen veranschaulicht die [Call](../../parallel/concrt/reference/call-class.md) und [Concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md) Klassen.  
  
 Im ersten Beispiel wird gezeigt, wie ein Lambda-Ausdruck an ein `call`-Objekt übergeben wird. Im zweiten Beispiel wird gezeigt, wie ein Funktionsobjekt an ein `call`-Objekt übergeben wird. Im dritten Beispiel wird gezeigt, wie eine Klassenmethode an ein `call`-Objekt gebunden wird.  
  
 Zu Illustrationszwecken wird in allen Beispielen dieses Themas die `call`-Klasse verwendet. Ein Beispiel, verwendet der `transformer` Klasse, finden Sie unter [wie: Verwenden von Transformer in einer Datenpipeline](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird aufgezeigt, wie die `call`-Klasse häufig verwendet wird. In diesem Beispiel wird eine Lambda-Funktion an den `call`-Konstruktor übergeben.  
  
 [!code-cpp[concrt-call-lambda#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_1.cpp)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
```Output  
13 squared is 169.  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel ähnelt dem vorherigen mit der Ausnahme, dass die `call`-Klasse zusammen mit einem Funktionsobjekt (Funktionselement) verwendet wird.  
  
 [!code-cpp[concrt-call-functor#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_2.cpp)]  
  
## <a name="example"></a>Beispiel  

 Im folgende Beispiel ähnelt der vorherigen Ansicht identisch, jedoch verwendet die [bind1st](../../standard-library/functional-functions.md#bind1st) und [Std:: mem_fun](../../standard-library/functional-functions.md#mem_fun) -Funktion zum Binden einer `call` Objekt an eine Klassenmethode.  

  
 Verwenden Sie diese Technik anstatt des Funktionsaufrufoperators, `call`, wenn Sie ein `transformer`- oder `operator()`-Objekt an eine bestimmte Klassenmethode binden möchten.  
  
 [!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]  
  
 Sie können auch das Ergebnis des Zuweisen der `bind1st` -Funktion eine [Std:: Function](../../standard-library/function-class.md) Objekts, oder verwenden die `auto` -Schlüsselwort, wie im folgenden Beispiel gezeigt.  
  
 [!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `call.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc / call.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)   
 [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Vorgehensweise: Verwenden von Transformer in einer Datenpipeline](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)   
 [Call-Klasse](../../parallel/concrt/reference/call-class.md)   
 [transformer-Klasse](../../parallel/concrt/reference/transformer-class.md)
