---
title: 'Vorgehensweise: direkt instanziieren von WRL-Komponenten | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: 1a9fa011-0cee-4abf-bf83-49adf53ff906
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6ecaebb2f846417f2fd3eeabdfe575d4d08a46fe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-instantiate-wrl-components-directly"></a>Gewusst wie: Direktes Instanziieren von WRL-Komponenten
Informationen zum Verwenden der Windows Runtime C++ Template Library (WRL)[Microsoft::WRL::Make](../windows/make-function.md) und [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md) Funktionen, um eine Komponente aus dem Modul instanziieren, definiert.  
  
 Durch die direkte Instanziierung von Komponenten können Sie den Mehraufwand reduzieren, wenn Klassenfactorys oder andere Mechanismen nicht benötigt werden. Sie können eine Komponente, die direkt in beide apps der universellen Windows-Plattform und desktop-apps instanziieren.  
  
 Gewusst wie: Verwenden von C++-Vorlagenbibliothek für Windows-Runtime zum Erstellen einer grundlegenden Komponente für Windows-Runtime und instanziieren es aus einer externen universelle Windows-Plattform-app finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer grundlegenden Komponente für die Windows-Runtime](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md). So verwenden Sie Windows Runtime C++ Template Library, zum Erstellen einer klassischen COM‑Komponente und instanziieren Sie es aus einer externen desktop-app finden Sie unter [Vorgehensweise: Erstellen einer klassischen COM-Komponente](../windows/how-to-create-a-classic-com-component-using-wrl.md).  
  
 Dieses Dokument enthält zwei Beispiele. Im ersten Beispiel wird eine Komponente mit der `Make`-Funktion instanziiert. Im zweiten Beispiel wird eine Komponente mit der `MakeAndInitialize`-Funktion instanziiert, die bei der Erstellung einen Fehler verursachen kann. (Da COM Fehler normalerweise mit `HRESULT`-Werten anstelle von Ausnahmen anzeigt, wird ein COM-Typ normalerweise nicht von seinem Konstruktor ausgelöst. `MakeAndInitialize` aktiviert eine Komponente, um ihre Konstruktionsargumente durch die `RuntimeClassInitialize`-Methode zu aktivieren.) Beide Beispiele definieren eine grundlegende Protokollierungsschnittstelle und implementieren diese Schnittstelle durch Definition einer Klasse, die Nachrichten an die Konsole ausgibt.  
  
> [!IMPORTANT]
>  Sie können keine der `new` Operator, um C++-Vorlagenbibliothek für Windows-Runtime-Komponenten zu instanziieren. Daher wird empfohlen, die direkte Instanziierung von Komponenten stets mit `Make` oder `MakeAndInitialize` vorzunehmen.  
  
### <a name="to-create-and-instantiate-a-basic-logger-component"></a>So erstellen und instanziieren Sie eine einfache Protokollierungskomponente  
  
1.  Erstellen Sie in Visual Studio eine **Win32-Konsolenanwendung** Projekt. Nennen Sie das Projekt, z. B. `WRLLogger`.  
  
2.  Hinzufügen einer **Midl-Datei (.idl)** -Datei in das Projekt, nennen Sie die Datei `ILogger.idl`, und fügen Sie diesen Code hinzu:  
  
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