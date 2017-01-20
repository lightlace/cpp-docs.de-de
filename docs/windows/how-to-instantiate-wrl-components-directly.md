---
title: "Gewusst wie: Direktes Instanziieren von WRL-Komponenten"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 1a9fa011-0cee-4abf-bf83-49adf53ff906
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Direktes Instanziieren von WRL-Komponenten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erfahren Sie, wie Sie mit den [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\-Funktionen \([!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)]\) [Microsoft::WRL::Make](../windows/make-function.md) und [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md) eine Komponente aus dem Modul instanziieren, das sie definiert.  
  
 Durch die direkte Instanziierung von Komponenten können Sie den Mehraufwand reduzieren, wenn Klassenfactorys oder andere Mechanismen nicht benötigt werden.  Sie können eine Komponente sowohl in [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-Apps als auch in Desktop\-Apps direkt instanziieren.  
  
 Wie Sie mit [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] eine grundlegende [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-Komponente erstellen und sie aus einer externen [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-App instanziieren, erfahren Sie unter [Exemplarische Vorgehensweise: Erstellen einer Basiskomponente für Windows\-Runtime](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md).  Wie Sie mit [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] eine klassische COM\-Komponente erstellen und sie aus einer externen Desktop\-App instanziieren, erfahren Sie unter [Gewusst wie: Erstellen einer klassischen COM\-Komponente](../windows/how-to-create-a-classic-com-component-using-wrl.md).  
  
 Dieses Dokument enthält zwei Beispiele.  Im ersten Beispiel wird eine Komponente mit der `Make`\-Funktion instanziiert.  Im zweiten Beispiel wird eine Komponente mit der `MakeAndInitialize`\-Funktion instanziiert, die bei der Erstellung einen Fehler verursachen kann. \(Da COM Fehler normalerweise mit `HRESULT`\-Werten anstelle von Ausnahmen anzeigt, wird ein COM\-Typ normalerweise nicht von seinem Konstruktor ausgelöst.  `MakeAndInitialize` aktiviert eine Komponente, um ihre Konstruktionsargumente durch die `RuntimeClassInitialize`\-Methode zu aktivieren.\) Beide Beispiele definieren eine grundlegende Protokollierungsschnittstelle und implementieren diese Schnittstelle durch Definition einer Klasse, die Nachrichten an die Konsole ausgibt.  
  
> [!IMPORTANT]
>  Mit dem Operator `new` können [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\-Komponenten nicht instanziiert werden.  Daher wird empfohlen, die direkte Instanziierung von Komponenten stets mit `Make` oder `MakeAndInitialize` vorzunehmen.  
  
### So erstellen und instanziieren Sie eine einfache Protokollierungskomponente  
  
1.  Erstellen Sie in Visual Studio ein Projekt der **Win32\-Konsolenanwendung**.  Geben Sie dem Projekt einen Namen, z. B. `WRLLogger`.  
  
2.  Fügen Sie dem Projekt eine **Midl\-Datei \(.idl\)** hinzu, nennen Sie die Datei `ILogger.idl`, und fügen Sie anschließend diesen Code hinzu:  
  
     [!CODE [wrl-logger-make#1](../CodeSnippet/VS_Snippets_Misc/wrl-logger-make#1)]  
  
3.  Ersetzen Sie den Inhalt von WRLLogger.cpp durch folgenden Code.  
  
     [!CODE [wrl-logger-make#2](../CodeSnippet/VS_Snippets_Misc/wrl-logger-make#2)]  
  
### So behandeln Sie Konstruktionsfehler für die grundlegende Protokollierungskomponente  
  
1.  Ersetzen Sie die Definition der `CConsoleWriter`\-Klasse durch folgenden Code.  Diese Version enthält eine private Zeichenfolgenmembervariable und überschreibt die `RuntimeClass::RuntimeClassInitialize`\-Methode.  `RuntimeClassInitialize` verursacht einen Fehler, wenn der Aufruf von `SHStrDup` einen Fehler verursacht.  
  
     [!CODE [wrl-logger-makeandinitialize#1](../CodeSnippet/VS_Snippets_Misc/wrl-logger-makeandinitialize#1)]  
  
2.  Ersetzen Sie die Definition von `wmain` durch folgenden Code.  Diese Version instanziiert das `CConsoleWriter`\-Objekt mit `MakeAndInitialize` und überprüft das `HRESULT`\-Ergebnis.  
  
     [!CODE [wrl-logger-makeandinitialize#2](../CodeSnippet/VS_Snippets_Misc/wrl-logger-makeandinitialize#2)]  
  
## Siehe auch  
 [Windows Runtime C\+\+ Template Library \(WRL\)](../windows/windows-runtime-cpp-template-library-wrl.md)   
 [Microsoft::WRL::Make](../windows/make-function.md)   
 [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md)