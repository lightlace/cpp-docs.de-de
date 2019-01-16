---
title: 'Vorgehensweise: Direktes Instanziieren von WRL-Komponenten'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1a9fa011-0cee-4abf-bf83-49adf53ff906
ms.openlocfilehash: 3caa29125de0de8cbe73379b8d7244206a5f9229
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336828"
---
# <a name="how-to-instantiate-wrl-components-directly"></a>Vorgehensweise: Direktes Instanziieren von WRL-Komponenten

Erfahren Sie, wie Sie mit der Windows Runtime C++ Template Library (WRL)[Microsoft::WRL::Make](make-function.md) und [Microsoft::WRL::Details::MakeAndInitialize](makeandinitialize-function.md) Funktionen, um eine Komponente aus dem Modul instanziieren, definiert.

Durch die direkte Instanziierung von Komponenten können Sie den Mehraufwand reduzieren, wenn Klassenfactorys oder andere Mechanismen nicht benötigt werden. Sie können eine Komponente, die direkt in beide Universal Windows Platform apps und desktop-apps instanziieren.

Gewusst wie: Verwenden von C++-Vorlagenbibliothek für Windows-Runtime zum Erstellen einer klassischen COM-Komponente, und instanziieren es aus einer externen desktop-app finden Sie unter [Vorgehensweise: Erstellen einer klassischen COM-Komponente](how-to-create-a-classic-com-component-using-wrl.md).

Dieses Dokument enthält zwei Beispiele. Im ersten Beispiel wird eine Komponente mit der `Make`-Funktion instanziiert. Im zweiten Beispiel wird eine Komponente mit der `MakeAndInitialize`-Funktion instanziiert, die bei der Erstellung einen Fehler verursachen kann. (Da COM HRESULT-Werte in der Regel anstelle von Ausnahmen verwendet, um anzugeben, Fehler, ein COM-Typ in der Regel aus seinem Konstruktor löst keine. `MakeAndInitialize` aktiviert eine Komponente, um ihre Konstruktionsargumente durch die `RuntimeClassInitialize`-Methode zu aktivieren.) Beide Beispiele definieren eine grundlegende Protokollierungsschnittstelle und implementieren diese Schnittstelle durch Definition einer Klasse, die Nachrichten an die Konsole ausgibt.

> [!IMPORTANT]
> Sie können keine der `new` Operator, um C++-Vorlagenbibliothek für Windows-Runtime-Komponenten zu instanziieren. Daher wird empfohlen, die direkte Instanziierung von Komponenten stets mit `Make` oder `MakeAndInitialize` vorzunehmen.

### <a name="to-create-and-instantiate-a-basic-logger-component"></a>So erstellen und instanziieren Sie eine einfache Protokollierungskomponente

1. Erstellen Sie in Visual Studio eine **Win32-Konsolenanwendung** Projekt. Nennen Sie das Projekt, z. B. *WRLLogger*.

2. Hinzufügen einer **Midl-Datei (.idl)** -Datei in das Projekt, nennen Sie die Datei `ILogger.idl`, und fügen Sie folgenden Code:

   [!code-cpp[wrl-logger-make#1](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_1.idl)]

3. Verwenden Sie den folgenden Code ersetzen Sie den Inhalt der `WRLLogger.cpp`.

   [!code-cpp[wrl-logger-make#2](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_2.cpp)]

### <a name="to-handle-construction-failure-for-the-basic-logger-component"></a>So behandeln Sie Konstruktionsfehler für die grundlegende Protokollierungskomponente

1. Ersetzen Sie die Definition der `CConsoleWriter`-Klasse durch folgenden Code. Diese Version enthält eine private Zeichenfolgenmembervariable und überschreibt die `RuntimeClass::RuntimeClassInitialize`-Methode. `RuntimeClassInitialize` verursacht einen Fehler, wenn der Aufruf von `SHStrDup` einen Fehler verursacht.

   [!code-cpp[wrl-logger-makeandinitialize#1](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_3.cpp)]

2. Ersetzen Sie die Definition von `wmain` durch folgenden Code. Diese Version verwendet `MakeAndInitialize` zum Instanziieren der `CConsoleWriter` Objekt aus, und überprüft das Ergebnis von HRESULT.

   [!code-cpp[wrl-logger-makeandinitialize#2](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_4.cpp)]

## <a name="see-also"></a>Siehe auch

[C++-Vorlagenbibliothek für Windows-Runtime (WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[Microsoft::WRL::Make](make-function.md)<br/>
[Microsoft::WRL::Details::MakeAndInitialize](makeandinitialize-function.md)