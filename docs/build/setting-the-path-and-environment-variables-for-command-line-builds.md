---
title: "Festlegen der Pfad- und Umgebungsvariablen f&#252;r Befehlszeilenbuilds | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
f1_keywords: 
  - "include"
  - "Lib"
  - "Path"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe-Compiler [C++], Umgebungsvariablen"
  - "Kompilieren von Quellcode [C++], Über die Befehlszeile"
  - "Umgebungsvariablen [C++]"
  - "Umgebungsvariablen [C++], CL-Compiler"
  - "INCLUDE (reserviertes Wort)"
  - "LIB-Umgebungsvariable"
  - "LINK-Tool [C++], Umgebungsvariablen"
  - "LINK-Tool [C++], Pfad"
  - "PATH (reserviertes Wort)"
  - "VCVARS32.bat (Datei)"
ms.assetid: 99389528-deb5-43b9-b99a-03c8773ebaf4
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Festlegen der Pfad- und Umgebungsvariablen f&#252;r Befehlszeilenbuilds
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Befehlszeilen\-Buildtools erfordern mehrere Umgebungsvariablen, die für Ihre Installation angepasst sind.  Wenn [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] installiert wird, werden mehrere Befehlsdateien erstellt, die die erforderlichen Umgebungsvariablen festlegen. Dann werden Verknüpfungen erstellt, die ein Eingabeaufforderungsfenster starten, in dem diese Variablen bereits festgelegt sind.  Wenn Sie die Befehlszeilentools verwenden möchten, können Sie eine dieser Verknüpfungen ausführen oder ein einfaches Eingabeaufforderungsfenster öffnen und dann die Befehlsdatei vcvarsall.bat ausführen.  
  
 Die [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Befehlszeilentools verwenden die Umgebungsvariablen PATH, TMP, INCLUDE, LIB und LIBPATH und können auch toolspezifische Umgebungsvariablen benutzen.  Da die Werte dieser Umgebungsvariablen für Ihre Installation spezifisch sind und durch Produktupdates und \-upgrades geändert werden können, empfehlen wir, dass Sie vcvarsall.bat oder eine Developer\-Eingabeaufforderungsverknüpfung verwenden, statt sie selbst festzulegen.  Informationen zu den speziellen vom Compiler und Linker verwendeten Umgebungsvariablen finden Sie unter [CL\-Umgebungsvariablen](../build/reference/cl-environment-variables.md) und [LINK\-Umgebungsvariablen](../build/reference/link-environment-variables.md).  
  
> [!NOTE]
>  Für mehrere Befehlszeilentools oder Tooloptionen sind Administratorberechtigungen erforderlich.  Um diese zu verwenden, sollten Sie ein Eingabeaufforderungsfenster öffnen, indem Sie die Option **Als Administrator ausführen** verwenden \(im Kontextmenü für das Eingabeaufforderungsfenster, das Sie öffnen möchten\).  
  
## Verwenden der Eingabeaufforderungsverknüpfungen  
 Die Developer\-Eingabeaufforderungsverknüpfung, die in jeder Edition [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] enthalten ist, öffnet ein Eingabeaufforderungsfenster und richtet die Umgebung für die Verwendung des x86\-systemeigenen 32\-Bit\-Toolsets für x86\-Prozessoren ein.  Eingabeaufforderungen für 32\-Bit\-Cross\-Compiler für x64\- und ARM\-Plattformen sind ebenfalls verfügbar.  Je nach System und installierter Edition von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] sind möglicherweise auch eine Eingabeaufforderungsverknüpfung für ein x64\-systemeigenes 64\-Bit\-Toolset für x64\-Prozessoren und eine für einen 64\-Bit\-Cross\-Compiler für x86\-Prozessoren verfügbar.  Die folgenden Versionen des Befehlszeilentoolsets sind in allen Editionen von Visual Studio verfügbar:  
  
 x86 auf x86  
 Erstellen Sie mit diesem Toolset Ausgabedateien für x86\-Computer.  Es wird auf x86\-Computern als systemeigener 32\-Bit\-Prozess, auf 64\-Bit\-Windows\-Betriebssystemen unter WOW64 ausgeführt.  
  
 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] unter x86 \([!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]\-Cross\-Compiler\)  
 Erstellen Sie mit diesem Toolset Ausgabedateien für [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)].  Es wird auf x86\-Computern als systemeigener 32\-Bit\-Prozess, auf 64\-Bit\-Windows\-Betriebssystemen unter WOW64 ausgeführt.  
  
 ARM auf x86 \(ARM\-Cross\-Compiler\)  
 Erstellen Sie mit diesem Toolset Ausgabedateien für ARM\-Computer.  Es wird auf x86\-Computern als systemeigener 32\-Bit\-Prozess, auf 64\-Bit\-Windows\-Betriebssystemen unter WOW64 ausgeführt.  
  
 Die folgenden Versionen des Befehlszeilentoolsets sind auf 64\-Bit\-Plattformen verfügbar:  
  
 x86 auf [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]  
 Erstellen Sie mit diesem Toolset Ausgabedateien für x86\-Computer.  Es wird als ein systemeigener Prozess in einem Windows\-64\-Bit\-Betriebssystem ausgeführt.  
  
 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] auf [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]  
 Erstellen Sie mit diesem Toolset Ausgabedateien für [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]\-Computer.  Es wird als ein systemeigener Prozess in einem Windows\-64\-Bit\-Betriebssystem ausgeführt.  
  
 ARM auf x64 \(ARM\-Cross\-Compiler\)  
 Erstellen Sie mit diesem Toolset Ausgabedateien für ARM\-Computer.  Es wird als ein systemeigener 64\-Bit\-Prozess in einem Windows\-64\-Bit\-Betriebssystem ausgeführt.  
  
#### So öffnen Sie ein Developer\-Befehlsaufforderungsfenster  
  
1.  Geben Sie auf dem Windows 8\-Startbildschirm Visual Studio\-Tools ein.  Beachten Sie, dass sich die Suchergebnisse während der Eingabe ändern. Wenn **Visual Studio\-Tools** angezeigt wird, wählen Sie die Option aus.  
  
     In früheren Versionen von Windows wählen Sie **Start** aus, und geben Sie dann in das Suchfeld Visual Studio\-Tools ein.  Wenn **Visual Studio\-Tools** in den Suchergebnissen angezeigt wird, wählen Sie die Option aus.  
  
2.  Öffnen Sie im Ordner **Visual Studio\-Tools** die **Developer\-Befehlsaufforderungg** für Ihre Version von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  \(Für die Ausführung als Administrator öffnen Sie das Kontextmenü für die Developer\-Eingabeaufforderung, und wählen Sie **Als Administrator ausführen** aus.\)  
  
 Die Developer\-Eingabeaufforderung richtet die Umgebung für die Verwendung des systemeigenen 32\-Bit\-Toolsets für x86\-Prozessoren ein.  Wählen Sie die **x64 Cross Tools\-Eingabeaufforderung** aus, um das systemeigene 32\-Bit\-Toolset für x64\-Prozessoren zu verwenden.  Wählen Sie die **ARM Cross Tools\-Eingabeaufforderung** aus, um das systemeigene 32\-Bit\-Toolset für ARM\-Prozessoren zu verwenden.  Wählen Sie die **x64 Native Tools\-Eingabeaufforderung** aus, um das systemeigene 64\-Bit\-Toolset für x64\-Prozessoren zu verwenden.  
  
## Verwenden von vcvarsall.bat in einem Eingabeaufforderungsfenster  
 Mit der Ausführung von vcvarsall.bat in einem einfachen Eingabeaufforderungsfenster können Sie Umgebungsvariablen für die Konfiguration der Befehlszeile für die systemeigene 32\-Bit\- oder 64\-Bit\-Kompilierung oder die Kreuzkompilierung an x86\-, x64\- oder ARM\-Prozessoren festlegen.  Wenn keine Argumente bereitgestellt werden, konfiguriert die vcvarsall.bat die Umgebungsvariablen für die Verwendung des systemeigenen 32\-Bit\-Compilers für x86\-Ziele.  Sie können damit aber auch alle anderen Compiler konfigurieren.  Wenn Sie eine Compilerkonfiguration angeben, die nicht installiert oder nicht auf der Buildcomputerarchitektur verfügbar ist, wird eine Meldung angezeigt.  In der folgenden Tabelle werden die unterstützten Argumente aufgeführt.  
  
|Vcvarsall.bat\-Argument|Compiler|Buildcomputerarchitektur|Buildausgabearchitektur|  
|-----------------------------|--------------|------------------------------|-----------------------------|  
|x86|x86\-32\-Bit systemeigen|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|x86|  
|x86\_amd64|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] auf x86\-Cross|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|x86\_arm|ARM auf x86\-Cross|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|ARM|  
|amd64|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 64\-Bit systemeigen|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|amd64\_x86|x86 auf [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]\-Cross|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|x86|  
|amd64\_arm|ARM auf [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]\-Cross|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|ARM|  
  
 Die folgenden Schritte zeigen, wie Sie eine Eingabeaufforderung für die Verwendung des systemeigenen 32\-Bit\-Toolsets für x86\-Plattformen konfigurieren.  
  
#### So führen Sie vcvarsall.bat aus  
  
1.  Wechseln Sie an der Eingabeaufforderung zum [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Installationsverzeichnis.  \(Der Speicherort hängt vom System und der [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-Installation ab, aber ein typischer Speicherort ist C:\\Program Files \(x86\)\\Microsoft Visual Studio *Version*\\VC\\.\) Geben Sie beispielsweise Folgendes ein:  
  
     cd "\\Program Files \(x86\)\\Microsoft Visual Studio 12.0\\VC"  
  
2.  Geben Sie zum Konfigurieren dieses Eingabeaufforderungsfensters für 32\-Bit\-x86\-Befehlszeilenbuilds an der Eingabeaufforderung Folgendes ein:  
  
     `vcvarsall x86`  
  
 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] stellt auch vcvars32.bat für die Einrichtung einer Befehlszeilenumgebung bereit.  Die vcvars32.bat\-Datei ist auf die Einrichtung der geeigneten Umgebungsvariablen für die Aktivierung von 32\-Bit\-x86\-Befehlszeilenbuilds beschränkt.  Sie entspricht dem Befehl `vcvarsall x86`.  
  
 Wenn Sie [DEVENV](../Topic/Devenv%20Command%20Line%20Switches.md) für Befehlszeilenbuilds verwenden wirkt sich die von vcvarsall.bat oder vcvars32.bat eingerichtete Umgebung nicht auf Ihre Builds aus, solange Sie nicht auch die Option **\/useenv** angeben.  
  
> [!CAUTION]
>  Die vcvarsall.bat\-Datei kann von Computer zu Computer unterschiedlich sein.  Ersetzen Sie eine fehlender oder beschädigte vcvarsall.bat\-Datei nicht durch eine Datei von einem anderen Computer.  Führen Sie stattdessen das [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-Setup erneut aus, um die fehlende Datei zu ersetzen.  
>   
>  Die vcvarsall.bat\-Datei ist auch von Version zu Version unterschiedlich.  Wenn die aktuelle Version von [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] auf einem Computer installiert ist, auf dem sich auch eine frühere Version von [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] befindet, führen Sie keine vcvarsall.bat oder vcvars32.bat aus den verschiedenen Version im selben Eingabeaufforderungsfenster aus.  
  
## Siehe auch  
 [Erstellen über die Befehlszeile](../build/building-on-the-command-line.md)   
 [Verknüpfung](../build/reference/linking.md)   
 [Linkeroptionen](../build/reference/linker-options.md)   
 [Kompilieren eines C\/C\+\+\-Programms](../build/reference/compiling-a-c-cpp-program.md)   
 [Compileroptionen](../build/reference/compiler-options.md)