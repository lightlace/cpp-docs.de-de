---
title: 'Vorgehensweise: Bereitstellen von Arbeitsfunktionen für die call- und transformer-Klassen'
ms.date: 11/04/2016
helpviewer_keywords:
- call class, example
- using the transformer class [Concurrency Runtime]
- using the call class [Concurrency Runtime]
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
ms.openlocfilehash: 4d2b7b3c88b51003a96526ef14d9940a8c26c3b3
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142489"
---
# <a name="how-to-provide-work-functions-to-the-call-and-transformer-classes"></a>Vorgehensweise: Bereitstellen von Arbeitsfunktionen für die call- und transformer-Klassen

In diesem Thema werden verschiedene Möglichkeiten zum Bereitstellen von Arbeitsfunktionen für die Klassen " [parallelcurrency:: Aufrufen](../../parallel/concrt/reference/call-class.md) " und " [parallelcurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md) " erläutert.

Im ersten Beispiel wird gezeigt, wie ein Lambdaausdruck an ein `call`-Objekt übergeben wird. Im zweiten Beispiel wird gezeigt, wie ein Funktionsobjekt an ein `call`-Objekt übergeben wird. Im dritten Beispiel wird gezeigt, wie eine Klassenmethode an ein `call`-Objekt gebunden wird.

Zu Illustrationszwecken wird in allen Beispielen dieses Themas die `call`-Klasse verwendet. Ein Beispiel, in dem die `transformer`-Klasse verwendet wird, finden Sie unter Gewusst [wie: Verwenden von Transformer in einer Daten Pipeline](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).

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

Das folgende Beispiel ähnelt dem vorherigen, mit der Ausnahme, dass die Funktionen [Std:: bind1st](../../standard-library/functional-functions.md#bind1st) und [Std:: mem_fun](../../standard-library/functional-functions.md#mem_fun) verwendet werden, um ein `call` Objekt an eine Klassenmethode zu binden.

Verwenden Sie diese Technik anstatt des Funktionsaufrufoperators, `call`, wenn Sie ein `transformer`- oder `operator()`-Objekt an eine bestimmte Klassenmethode binden möchten.

[!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]

Sie können das Ergebnis der `bind1st` Funktion auch einem [Std:: function](../../standard-library/function-class.md) -Objekt zuweisen oder das `auto`-Schlüsselwort verwenden, wie im folgenden Beispiel gezeigt.

[!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `call.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio-Eingabe Aufforderungs Fenster aus.

> **cl. exe/EHsc "Call. cpp"**

## <a name="see-also"></a>Weitere Informationen

[Asynchrone Agents Library](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Vorgehensweise: Verwenden von transformer in einer Datenpipeline](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br/>
[call-Klasse](../../parallel/concrt/reference/call-class.md)<br/>
[transformer-Klasse](../../parallel/concrt/reference/transformer-class.md)
