---
title: "Gewusst wie: Konfigurieren von Visual C++-Projekten f&#252;r 64-Bit-Zielplattformen"
ms.custom: na
ms.date: "12/14/2016"
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
  - "Plattformen [C++], 64-Bit"
  - "64-Bit-Programmierung [C++], Konfigurieren von Projekten"
  - "Projektkonfigurationen [C++]"
ms.assetid: 2b9ae001-df36-4750-83b2-982145d632ad
caps.latest.revision: 22
caps.handback.revision: "22"
ms.author: "corob"
manager: "ghogen"
---
# Gewusst wie: Konfigurieren von Visual C++-Projekten f&#252;r 64-Bit-Zielplattformen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können die Projektkonfigurationen in Visual Studio verwenden, um C\+\+\-Anwendungen für 64\-Bit\-Zielplattformen einzurichten. Außerdem können Sie Win32\-Projekteinstellungen zu einer 64\-Bit\-Projektkonfiguration migrieren.  
  
### So richten Sie C\+\+\-Anwendungen für 64\-Bit\-Zielplattformen ein  
  
1.  Öffnen Sie das C\+\+\-Projekt, das Sie konfigurieren möchten.  
  
2.  Öffnen Sie die Eigenschaftenseiten für das betreffende Projekt. Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../misc/how-to-open-project-property-pages.md).  
  
    > [!NOTE]
    >  Achten Sie bei .NET\-Projekten darauf, dass im Dialogfeld **\<Projektname\>\-Eigenschaftenseiten** der Knoten **Konfigurationseigenschaften** oder einer seiner Unterknoten ausgewählt ist; andernfalls ist die Schaltfläche **Konfigurations\-Manager** nicht verfügbar.  
  
3.  Wählen Sie die Schaltfläche **Konfigurations\-Manager** aus, um das Dialogfeld **Konfigurations\-Manager** zu öffnen.  
  
4.  Wählen Sie in der Dropdownliste **Aktive Projektmappenplattform** die Option **\<Neu…\>** aus, um das Dialogfeld **Neue Projektmappenplattform** zu öffnen.  
  
5.  Wählen Sie in der Dropdownliste **Neue Plattform eingeben oder auswählen** eine 64\-Bit\-Plattform aus.  
  
    > [!NOTE]
    >  Im Dialogfeld **Neue Projektmappenplattform** können Sie die Option **Einstellungen kopieren von** verwenden, um vorhandene Projekteinstellungen in die neue 64\-Bit\-Projektkonfiguration zu kopieren.  
  
6.  Klicken Sie auf die Schaltfläche **OK**. Die Plattform, die Sie im vorherigen Schritt ausgewählt haben, wird unter **Aktive Projektmappenplattform** im Dialogfeld **Konfigurations\-Manager** angezeigt.  
  
7.  Wählen Sie im Dialogfeld **Konfigurations\-Manager** die Schaltfläche **Schließen** aus, und wählen Sie dann im Dialogfeld **\<Projektname\>\-Eigenschaftenseiten** die Schaltfläche **OK** aus.  
  
### So kopieren Sie Win32\-Projekteinstellungen in eine 64\-Bit\-Projektkonfiguration  
  
-   Wenn das Dialogfeld **Neue Projektmappenplattform** geöffnet ist, während Sie ein Projekt für eine 64\-Bit\-Zielplattform einrichten, wählen Sie in der Dropdownliste **Einstellungen kopieren von** den Wert **Win32** aus. Diese Projekteinstellungen werden auf der Projektebene automatisch aktualisiert:  
  
    -   Die Linkeroption [\/MACHINE](../build/reference/machine-specify-target-platform.md) wird auf **\/MACHINE:X64** festgelegt.  
  
    -   **Ausgabe registrieren** ist deaktiviert. Weitere Informationen finden Sie unter [Eigenschaftenseiten "Linker"](../ide/linker-property-pages.md).  
  
    -   **Zielumgebung** wird auf **\/env x64** festgelegt. Weitere Informationen finden Sie unter [Eigenschaftenseiten "MIDL": "Allgemein"](../ide/midl-property-pages-general.md).  
  
    -   **Parameter überprüfen** wird deaktiviert und auf den Standardwert zurückgesetzt. Weitere Informationen finden Sie unter [Eigenschaftenseiten "MIDL": "Erweitert"](../ide/midl-property-pages-advanced.md).  
  
    -   Wenn **Debuginformationsformat** in der Win32\-Projektkonfiguration auf **\/ZI** festgelegt war, wird der Wert in der 64\-Bit\-Projektkonfiguration auf **\/Zi** festgelegt. Weitere Informationen finden Sie unter [\/Z7, \/Zi, \/ZI \(Debuginformationsformat\)](../build/reference/z7-zi-zi-debug-information-format.md).  
  
    > [!NOTE]
    >  Keine dieser Projekteigenschaften wird geändert, wenn sie auf der Dateiebene überschrieben werden.  
  
## Siehe auch  
 [64\-Bit\-Anwendungen](../Topic/64-bit%20Applications.md)   
 [Konfigurieren von Programmen für 64\-Bit](../build/configuring-programs-for-64-bit-visual-cpp.md)   
 [Debuggen von 64\-Bit\-Anwendungen](../Topic/Debug%2064-Bit%20Applications.md)