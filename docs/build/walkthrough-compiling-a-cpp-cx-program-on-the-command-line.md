---
title: 'Exemplarische Vorgehensweise: Kompilieren eines c++ / CX-Programms in der Befehlszeile | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 626f5544-69ed-4736-83a9-f11389b371b2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0963f70047ea42893b1169c5da7c614766406280
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="walkthrough-compiling-a-ccx-program-on-the-command-line"></a>Exemplarische Vorgehensweise: Kompilieren eines C++/CX-Programms in der Befehlszeile
Sie können Visual C++-Programme erstellen, die auf die Windows Runtime abzielen und diese in der Befehlszeile erstellen. Visual C++ unterstützt Visual C++-Komponentenerweiterungen (C++/CX), die zusätzliche Typen und Operatoren für das Windows-Runtime-Programmiermodell bereitstellen. Sie können C + c++ / CX-apps für die universelle Windows-Plattform (UWP), Windows Phone 8.1 und Windows Desktop zu erstellen. Weitere Informationen finden Sie unter [Tour von c++ ein c++ / CX](http://msdn.microsoft.com/magazine/dn166929.aspx) und [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md).  
  
 In dieser exemplarischen Vorgehensweise verwenden Sie einen Texteditor zur Erstellung eines grundlegenden C++/CX-Programms und kompilieren es dann auf der Befehlszeile. (Sie können Sie Ihr C++/CX-Programm verwenden, statt das gezeigte einzugeben oder Sie können ein C++/CX-Codebeispiel aus einem anderen Hilfeartikel verwenden. Diese Technik ist nützlich zum Erstellen und Testen von kleinen Modulen, die keine Benutzeroberflächenelemente enthalten.)  
  
> [!NOTE]
>  Sie können auch die Visual Studio IDE für die Kompilierung von C++/CX-Programmen verwenden. Da die IDE enthält entwerfen, Debuggen, Emulation und Unterstützung für die Bereitstellung, die nicht in der Befehlszeile verfügbar ist, wird empfohlen, dass Sie die IDE verwenden, um apps der universellen Windows-Plattform (UWP) zu erstellen. Weitere Informationen finden Sie unter [erstellen eine uwp-app in C++](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Sie benötigen grundlegende Kenntnisse der Programmiersprache C++.  
  
## <a name="compiling-a-ccx-program"></a>Kompilieren eines C++/CX-Programms  
 So aktivieren Sie die Kompilierung für c++ / CX, verwenden Sie die [/Zw](../build/reference/zw-windows-runtime-compilation.md) (Compileroption). Der Visual C++-Compiler generiert eine .exe-Datei, die auf die Windows Runtime abzielt und mit den erforderlichen Bibliotheken verknüpft wird.  
  
#### <a name="to-compile-a-ccx-application-on-the-command-line"></a>So kompilieren Sie eine C++/CX-Anwendung in der Befehlszeile  
  
1.  Öffnen einer **Entwicklereingabeaufforderung** Fenster. (Auf der **starten** geöffnete Fenster **Apps**. Öffnen der **Visual Studio-Tools** Ordner unter Ihrer Version von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], und wählen Sie dann die **Entwicklereingabeaufforderung** Verknüpfung.) Weitere Informationen zu einer Developer-Eingabeaufforderungsfenster zu öffnen, finden Sie unter [Erstellen von C/C++-Code in der Befehlszeile](../build/building-on-the-command-line.md).  
  
     Administratoranmeldeinformationen sind möglicherweise erforderlich, um den Code abhängig vom Betriebssystem und der Konfiguration des Computers zu kompilieren. Im Eingabeaufforderungsfenster als Administrator ausführen möchten, öffnen Sie im Kontextmenü für **Entwicklereingabeaufforderung** und wählen Sie dann **als Administrator ausführen**.  
  
2.  Geben Sie an der Eingabeaufforderung **Editor basiccx.cpp**.  
  
     Wählen Sie **Ja** Wenn Sie zum Erstellen einer Datei aufgefordert werden.  
  
3.  Geben Sie die folgenden Zeilen in Notepad ein:  
  
    ```cpp  
    using namespace Platform;  
  
    int main(Platform::Array<Platform::String^>^ args)  
    {  
        Platform::Details::Console::WriteLine("This is a C++/CX program.");  
    }  
  
    ```  
  
4.  Wählen Sie in der Menüleiste **Datei**, **speichern**.  
  
     Sie erstellt haben, die Windows-Runtime verwendet Visual C++-Quelldatei [plattformnamespace](../cppcx/platform-namespace-c-cx.md) Namespace.  
  
5.  Geben Sie an der Eingabeaufforderung **cl/EHsc/Zw basiccx.cpp/Link/Subsystem: Console**. Der cl.exe-Compiler kompiliert den Quellcode in eine .obj-Datei und führt dann den Linker aus, um ein ausführbares Programm namens basiccx.exe zu generieren. (Die [/EHsc /](../build/reference/eh-exception-handling-model.md) (Compileroption) gibt an, die C++-Ausnahmebehandlungsmodell und das [/link](../build/reference/link-pass-options-to-linker.md) -Flag gibt an, eine Konsolenanwendung.)  
  
6.  Zum Ausführen des basiccx.exe-Programms an der Eingabeaufforderung eingeben **Basiccx**.  
  
     Das Programm zeigt folgenden Text an und wird anschließend beendet:  
  
    ```Output  
    This is a C++/CX program.  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)   
 [Compileroptionen](../build/reference/compiler-options.md)