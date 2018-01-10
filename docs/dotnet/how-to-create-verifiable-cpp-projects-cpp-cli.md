---
title: "Vorgehensweise: Erstellen überprüfbarer C++-Projekte (C + c++ / CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- verifiable assemblies [C++], creating
- conversions, C++ projects
- Visual C++ projects
ms.assetid: 4ef2cc1a-e3e5-4d67-8d8d-9c614f8ec5d3
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4d6a7806183766d96c0d106d9d9e890b046f4563
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-verifiable-c-projects-ccli"></a>Gewusst wie: Erstellen überprüfbarer C++-Projekte (C++/CLI)
Visual C++-Anwendungs-Assistenten keine überprüfbar Projekte erstellen, aber Projekte konvertiert werden können, um überprüfbar zu sein. In diesem Thema wird beschrieben, wie Projekteigenschaften festlegen und ändern die Quelle der Projektdateien zum Transformieren der Visual C++-Projekte zur überprüfbare Anwendung löst.  
  
## <a name="compiler-and-linker-settings"></a>Compiler und Linker-Einstellungen  
 Standardmäßig .NET Projekte verwenden das compilerkennzeichen "/ CLR" und den Linker Zielhardware X86 konfigurieren. Für überprüfbaren Code müssen Sie das Flag/CLR: safe verwenden, und Sie müssen den Linker an, für die Generierung von MSIL anstatt systemeigene maschinenanweisungen anweisen.  
  
#### <a name="to-change-the-compiler-and-linker-settings"></a>So ändern Sie die Einstellungen für Compiler und linker  
  
1.  Zeigen Sie die Eigenschaftenseite des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).  
  
2.  Auf der **allgemeine** Seite der **Konfigurationseigenschaften** Knotensatz, der **Common Language Runtime-Unterstützung** Eigenschaft **Sichere MSIL Common Language Runtime-Unterstützung (/ CLR: safe)**.  
  
3.  Auf der **erweitert** Seite unter der **Linker** , durch das Festlegen der **CLR-Imagetyps** Eigenschaft **sicheres IL-Bild erzwingen (/ CLRIMAGETYPE: safe)**.  
  
## <a name="removing-native-data-types"></a>Entfernen von systemeigenen Datentypen  
 Da die systemeigenen Datentypen nicht überprüfbar sind, auch wenn sie nicht tatsächlich verwendet werden, müssen Sie alle Header-Dateien, die mit systemeigenen Typen entfernen.  
  
> [!NOTE]
>  Das folgende Verfahren gilt für Windows Forms-Anwendung (.NET) und die Konsole (.NET) Projekte.  
  
#### <a name="to-remove-references-to-native-data-types"></a>So entfernen Sie Verweise auf die systemeigenen Datentypen  
  
1.  Kommentieren Sie alles in der Datei "stdafx.h".  
  
## <a name="configuring-an-entry-point"></a>Konfigurieren eines Einstiegspunktes  
 Da C-Laufzeitbibliotheken (CRT) nicht überprüfbare Anwendungen verwenden können, können nicht sie CRT, rufen Sie die main-Funktion als standard Einstiegspunkt abhängig sind. Dies bedeutet, dass Sie den Namen der Funktion, die anfänglich aufgerufen werden, an den Linker explizit angeben müssen. (In diesem Fall Main() statt main() oder _tmain () verwendet, um einen nicht-CRT-Einstiegspunkt anzugeben, aber da Einstiegspunkt explizit angegeben werden muss, ist dieser Name willkürlich.)  
  
> [!NOTE]
>  Die folgenden Verfahren gelten für Konsole (.NET) Projekte.  
  
#### <a name="to-configure-an-entry-point"></a>So konfigurieren Sie einen Einstiegspunkt  
  
1.  Ändern Sie _tmain () in Main() in der wichtigsten cpp-Datei des Projekts.  
  
2.  Zeigen Sie die Eigenschaftenseite des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).  
  
3.  Auf der **erweitert** Seite unter das **Linker** Knoten, geben Sie `Main` als die **Einstiegspunkt** Eigenschaftswert.  
  
## <a name="see-also"></a>Siehe auch  
 [Reiner und überprüfbarer Code (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)