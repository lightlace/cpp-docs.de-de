---
title: "Gewusst wie: Aktivieren eines 64-Bit-Visual C++-Toolsets auf der Befehlszeile"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "64-Bit-Compiler [C++], Befehlszeile verwenden"
  - "64-Bit-Compiler [C++], Toolsetaktivierung über die Befehlszeile"
  - "Befehlszeile [C++], 64-Bit-Compiler"
  - "IPF"
  - "IPF, Befehlszeilencompiler"
  - "Itanium [C++]"
  - "Itanium [C++], Befehlszeilencompiler"
  - "x64 [C++]"
  - "x64 [C++], Befehlszeilencompiler"
ms.assetid: 4da93a19-e20d-4778-902a-5eee9a6a90b5
caps.latest.revision: 30
caps.handback.revision: "30"
ms.author: "corob"
manager: "ghogen"
---
# Gewusst wie: Aktivieren eines 64-Bit-Visual C++-Toolsets auf der Befehlszeile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ enthält Compiler, mit denen Sie Apps erstellen können, die auf 32\-Bit\- oder 64\-Bit\-Plattformen oder auf einem ARM\-basierten Windows\-Betriebssystem ausgeführt werden können.  
  
> [!NOTE]
>  Informationen zu den spezifischen Tools, die in den Visual C\+\+\-Edition enthalten sind, finden Sie unter [Visual C\+\+\-Tools und \-Vorlagen in Visual Studio\-Editionen](../ide/visual-cpp-tools-and-templates-in-visual-studio-editions.md).  
>   
>  Informationen zum Verwenden der Visual Studio\-IDE zum Erstellen von 64\-Bit\-Anwendungen finden Sie unter [Gewusst wie: Konfigurieren von Visual C\+\+\-Projekten für 64\-Bit\-Zielplattformen](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).  
  
 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] enthält 32\-Bit, x86\-gehostete, systemeigene und Cross\-Compiler für x86\-, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]\- und ARM\-Ziele.  Wenn [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] auf einem 64\-Bit\-Windows\-Betriebssystem installiert ist, werden 32\-Bit, x86\-gehostete systemeigene und Cross\-Compiler sowie 64\-Bit, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]\-gehostete systemeigene und Cross\-Compiler für jedes Ziel \(x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] und ARM\) installiert.  Die 32\-Bit\- und die 64\-Bit\-Compiler generieren für alle Ziele einen identischen Code. Allerdings unterstützen die 64\-Bit\-Compiler mehr Speicher für vorkompilierte Headersymbole und die Optimierung des gesamten Programms \([\/GL](../build/reference/gl-whole-program-optimization.md)\-, [\/LTCG](../build/reference/ltcg-link-time-code-generation.md)\-Optionen\).  Wenn Sie bei einem 32\-Bit\-Compiler auf Speicherbegrenzungen treffen, versuchen Sie es mit einem 64\-Bit\-Compiler.  
  
 Wenn Visual Studio auf einem 64\-Bit\-Betriebssystem von Windows installiert wird, stehen zusätzliche Verknüpfungen der Eingabeaufforderung für die 64\-Bit [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]\-eigenen und x86\-Cross\-Compiler zur Verfügung.  Zum Zugreifen auf diese Eingabeaufforderungen unter Windows 8 klicken Sie auf dem **Start**\-Bildschirm auf **Alle Apps**.  Öffnen Sie in der installierten Version von **[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]** die **Visual Studio\-Tools**, und wählen Sie dann eine der systemeigenen Tool\- oder Cross\-Tool\-Eingabeaufforderungen.  Bei früheren Windows\-Versionen wählen Sie **Start**, erweitern **Alle Programme**, **[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]**, **Visual Studio\-Tools**, und wählen dann eine Eingabeaufforderung.  
  
## Vcvarsall.bat  
 Alle Compiler können in der Befehlszeile verwendet werden, indem Sie die vcvarsall.bat\-Befehlsdatei ausführen, um die Pfad\- und Umgebungsvariablen zu konfigurieren, die das Compilertoolset aktivieren.  Da es keine Verknüpfungen für Eingabeaufforderungen gibt, um ein 64\-Bit\-Toolset auf x86\- oder ARM\-Zielplattformen zu aktivieren, verwenden Sie vcvarsall.bat in einem Eingabeaufforderungsfenster, um stattdessen das 64\-Bit\-Toolset zu verwenden.  Weitere Informationen finden Sie unter [Festlegen der Pfad\- und Umgebungsvariablen für Befehlszeilenbuilds](../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  
  
 Die folgenden Schritte zeigen, wie Sie eine Eingabeaufforderung konfigurieren, um das native 64\-Bit\-Toolset für x86\-, x64\- und ARM\-Zielplattformen zu verwenden.  
  
#### So führen Sie vcvarsall.bat für die Verwendung eines 64\-Bit\-Toolsets aus  
  
1.  Wechseln Sie bei Eingabeaufforderung zum [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Installationsverzeichnis.  \(Der Speicherort ist vom System und der [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-Installation abhängig, doch ein typischer Speicherort ist C:\\Programme \(x86\)\\Microsoft Visual Studio *Version*\\VC\\.\) Geben Sie beispielsweise Folgendes ein:  
  
     cd "\\Programme \(x86\)\\Microsoft Visual Studio 12.0\\VC"  
  
2.  Geben Sie bei Eingabeaufforderung Folgendes ein, um dieses Eingabeaufforderungsfenster für 64\-Bit\-Befehlszeilen\-Builds mit x64\-Zielplattformen zu konfigurieren:  
  
     `vcvarsall amd64`  
  
3.  Geben Sie bei Eingabeaufforderung Folgendes ein, um dieses Eingabeaufforderungsfenster für 64\-Bit\-Befehlszeilen\-Builds mit x86\-Zielplattformen zu konfigurieren:  
  
     `vcvarsall amd64_x86`  
  
4.  Geben Sie bei Eingabeaufforderung Folgendes ein, um dieses Eingabeaufforderungsfenster für 64\-Bit\-Befehlszeilen\-Builds mit ARM\-Zielplattformen zu konfigurieren:  
  
     `vcvarsall amd64_arm`  
  
## Siehe auch  
 [Konfigurieren von Programmen für 64\-Bit](../build/configuring-programs-for-64-bit-visual-cpp.md)