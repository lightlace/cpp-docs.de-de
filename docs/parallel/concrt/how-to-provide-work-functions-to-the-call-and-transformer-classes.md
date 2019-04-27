---
title: 'Vorgehensweise: Bereitstellen von Arbeitsfunktionen für die Call- und Transformer-Klassen'
ms.date: 11/04/2016
helpviewer_keywords:
- call class, example
- using the transformer class [Concurrency Runtime]
- using the call class [Concurrency Runtime]
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
ms.openlocfilehash: c41c29dae277105f268171503e662e2a02e3857e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62205789"
---
# <a name="how-to-provide-work-functions-to-the-call-and-transformer-classes"></a>Vorgehensweise: Bereitstellen von Arbeitsfunktionen für die Call- und Transformer-Klassen

In diesem Thema veranschaulicht verschiedene Möglichkeiten zum Bereitstellen von Arbeitsfunktionen der [Concurrency:: Call](../../parallel/concrt/reference/call-class.md) und [Concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md) Klassen.

Im ersten Beispiel wird gezeigt, wie ein Lambdaausdruck an ein `call`-Objekt übergeben wird. Im zweiten Beispiel wird gezeigt, wie ein Funktionsobjekt an ein `call`-Objekt übergeben wird. Im dritten Beispiel wird gezeigt, wie eine Klassenmethode an ein `call`-Objekt gebunden wird.

Zu Illustrationszwecken wird in allen Beispielen dieses Themas die `call`-Klasse verwendet. Ein Beispiel für die Verwendung der `transformer` Klasse, finden Sie unter [Vorgehensweise: Verwenden von Transformer in einer Datenpipeline](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).

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

Das folgende Beispiel ähnelt dem vorherigen Beispiel, außer dass mithilfe der [bind1st](../../standard-library/functional-functions.md#bind1st) und [Std:: mem_fun](../../standard-library/functional-functions.md#mem_fun) -Funktion zum Binden einer `call` Objekt an eine Klassenmethode.

Verwenden Sie diese Technik anstatt des Funktionsaufrufoperators, `call`, wenn Sie ein `transformer`- oder `operator()`-Objekt an eine bestimmte Klassenmethode binden möchten.

[!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]

Sie können auch das Ergebnis des Zuweisen der `bind1st` -Funktion eine [Std:: Function](../../standard-library/function-class.md) Objekts, oder Verwenden der `auto` -Schlüsselwort, wie im folgenden Beispiel gezeigt.

[!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `call.cpp` und führen Sie dann den folgenden Befehl in einem Fenster von Visual Studio-Eingabeaufforderung.

**CL.exe/EHsc call.cpp**

## <a name="see-also"></a>Siehe auch

[Asynchrone Agents Library](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Vorgehensweise: Verwenden von „transformer“ in einer Datenpipeline](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br/>
[call-Klasse](../../parallel/concrt/reference/call-class.md)<br/>
[transformer-Klasse](../../parallel/concrt/reference/transformer-class.md)
