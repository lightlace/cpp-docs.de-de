---
title: 'Vorgehensweise: Direktes Instanziieren von WRL-Komponenten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 1a9fa011-0cee-4abf-bf83-49adf53ff906
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 40904f8379d1a11d26c29af2340fa4adb24f12e0
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39568815"
---
# <a name="how-to-instantiate-wrl-components-directly"></a>Gewusst wie: Direktes Instanziieren von WRL-Komponenten
Erfahren Sie, wie Sie mit der Windows Runtime C++ Template Library (WRL)[Microsoft::WRL::Make](../windows/make-function.md) und [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md) Funktionen, um eine Komponente aus dem Modul instanziieren, definiert.  
  
 Durch die direkte Instanziierung von Komponenten können Sie den Mehraufwand reduzieren, wenn Klassenfactorys oder andere Mechanismen nicht benötigt werden. Sie können eine Komponente, die direkt in beide Universal Windows Platform apps und desktop-apps instanziieren.  
  
Gewusst wie: Verwenden von C++-Vorlagenbibliothek für Windows-Runtime zum Erstellen einer klassischen COM-Komponente, und instanziieren es aus einer externen desktop-app finden Sie unter [Vorgehensweise: Erstellen einer klassischen COM-Komponente](../windows/how-to-create-a-classic-com-component-using-wrl.md).  
  
 Dieses Dokument enthält zwei Beispiele. Im ersten Beispiel wird eine Komponente mit der `Make`-Funktion instanziiert. Im zweiten Beispiel wird eine Komponente mit der `MakeAndInitialize`-Funktion instanziiert, die bei der Erstellung einen Fehler verursachen kann. (Da COM HRESULT-Werte in der Regel anstelle von Ausnahmen verwendet, um anzugeben, Fehler, ein COM-Typ in der Regel aus seinem Konstruktor löst keine. `MakeAndInitialize` aktiviert eine Komponente, um ihre Konstruktionsargumente durch die `RuntimeClassInitialize`-Methode zu aktivieren.) Beide Beispiele definieren eine grundlegende Protokollierungsschnittstelle und implementieren diese Schnittstelle durch Definition einer Klasse, die Nachrichten an die Konsole ausgibt.  
  
> [!IMPORTANT]
>  Können keine der **neue** Operator, um C++-Vorlagenbibliothek für Windows-Runtime-Komponenten zu instanziieren. Daher wird empfohlen, die direkte Instanziierung von Komponenten stets mit `Make` oder `MakeAndInitialize` vorzunehmen.  
  
### <a name="to-create-and-instantiate-a-basic-logger-component"></a>So erstellen und instanziieren Sie eine einfache Protokollierungskomponente  
  
1.  Erstellen Sie in Visual Studio eine **Win32-Konsolenanwendung** Projekt. Nennen Sie das Projekt, z. B. `WRLLogger`.  
  
2.  Hinzufügen einer **Midl-Datei (.idl)** -Datei in das Projekt, nennen Sie die Datei `ILogger.idl`, und fügen Sie folgenden Code:  
  
     [!code-cpp[wrl-logger-make#1](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_1.idl)]  
  
3.  Ersetzen Sie den Inhalt von WRLLogger.cpp durch folgenden Code.  
  
     [!code-cpp[wrl-logger-make#2](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_2.cpp)]  
  
### <a name="to-handle-construction-failure-for-the-basic-logger-component"></a>So behandeln Sie Konstruktionsfehler für die grundlegende Protokollierungskomponente  
  
1.  Ersetzen Sie die Definition der `CConsoleWriter`-Klasse durch folgenden Code. Diese Version enthält eine private Zeichenfolgenmembervariable und überschreibt die `RuntimeClass::RuntimeClassInitialize`-Methode. `RuntimeClassInitialize` verursacht einen Fehler, wenn der Aufruf von `SHStrDup` einen Fehler verursacht.  
  
     [!code-cpp[wrl-logger-makeandinitialize#1](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_3.cpp)]  
  
2.  Ersetzen Sie die Definition von `wmain` durch folgenden Code. Diese Version instanziiert das `MakeAndInitialize`-Objekt mit `CConsoleWriter` und überprüft das `HRESULT`-Ergebnis.  
  
     [!code-cpp[wrl-logger-makeandinitialize#2](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_4.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Runtime C++-Vorlagenbibliothek (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)   
 [Microsoft::wrl::Make](../windows/make-function.md)   
 [Microsoft::wrl::Details::MakeAndInitialize](../windows/makeandinitialize-function.md)