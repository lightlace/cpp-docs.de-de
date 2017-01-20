---
title: "Gewusst wie: Kompilieren von MFC-Code und ATL-Code mit /clr"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr-Compileroption [C++], Kompilieren von ATL- und MFC-Code"
  - "ATL [C++], Interoperabilität"
  - "Erweiterungs-DLLs [C++], /clr-Compileroption"
  - "Interop [C++], /clr-Compileroption"
  - "Interoperabilität [C++], /clr-Compileroption"
  - "MFC [C++], Interoperabilität"
  - "Gemischte Assemblys [C++], ATL-Code"
  - "Gemischte Assemblys [C++], MFC-Code"
  - "Reguläre DLLs [C++], /clr-Compileroption"
ms.assetid: 12464bec-33a4-482c-880a-c078de7f6ea5
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Kompilieren von MFC-Code und ATL-Code mit /clr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Thema behandelt das Kompilieren vorhandener MFC\- und ATL\-Programme für die Common Language Runtime.  
  
### So kompilieren Sie eine ausführbare MFC\-Datei oder eine reguläre DLL mittels \/clr  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften**.  
  
2.  Erweitern Sie im Dialogfeld **Projekteigenschaften** den Knoten neben den **Konfigurationseigenschaften**, und wählen Sie **Allgemein** aus.  Legen Sie im rechten Bereich unter **Projektstandards** die **Common Language Runtime\-Unterstützung** auf **Common Language Runtime\-Unterstützung \(\/clr\)** fest.  
  
     Legen Sie im gleichen Fenster die Option **Verwendung von MFC** auf **MFC in einer gemeinsam genutzten DLL verwenden** fest.  
  
3.  Erweitern Sie unter **Konfigurationseigenschaften** den Knoten neben **C\/C\+\+**, und wählen Sie **Allgemein** aus.  Das **Debuginformationsformat** muss auf **Programmdatenbank \/Zi** \(nicht auf **\/ZI**\) festgelegt sein.  
  
4.  Wählen Sie den Knoten **Codegenerierung** aus.  Legen Sie **Minimale Neuerstellung aktivieren** auf **Nein \(\/Gm\-\)** fest.  Legen Sie auch **Vollständige Laufzeitüberprüfungen** auf **Standard** fest.  
  
5.  Wählen Sie unter **Konfigurationseigenschaften** die Option **C\/C\+\+** und dann **Codegenerierung**.  Die **Laufzeitbibliothek** muss entweder auf **Multithreaded\-Debug\-DLL \(\/MDd\)** oder auf **Multithreaded\-DLL \(\/MD\)** festgelegt sein.  
  
6.  Fügen Sie in der Datei "Stdafx.h" die folgende Zeile hinzu.  
  
    ```  
    #using <System.Windows.Forms.dll>  
    ```  
  
### So kompilieren Sie eine MFC\-Erweiterungs\-DLL mittels \/clr  
  
1.  Folgen Sie den Anweisungen unter "So kompilieren Sie eine ausführbare MFC\-Datei oder eine reguläre DLL mittels \/clr".  
  
2.  Erweitern Sie unter **Konfigurationseigenschaften** den Knoten neben **C\/C\+\+**, und wählen Sie **Vorkompilierte Header** aus.  Legen Sie für **Erstellen\/Verwenden eines vorkompilierten Headers** die Option **Vorkompilierte Header nicht verwenden** fest.  
  
     Klicken Sie alternativ im **Projektmappen\-Explorer** mit der rechten Maustaste auf "Stdafx.cpp", und klicken Sie dann auf **Eigenschaften**.  Erweitern Sie unter **Konfigurationseigenschaften** den Knoten neben **C\/C\+\+**, und wählen Sie **Allgemein** aus.  Legen Sie **Mit Unterstützung für Common Language Runtime kompilieren** auf **Keine Common Language Runtime\-Unterstützung** fest.  
  
3.  Im Falle der DllMain enthaltenden Datei und alle von ihr aufgerufenen Objekte klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf die Datei, und klicken Sie auf **Eigenschaften**.  Erweitern Sie unter **Konfigurationseigenschaften** den Knoten neben **C\/C\+\+**, und wählen Sie **Allgemein** aus.  Legen Sie im rechten Bereich unter **Projektstandards** die Option **Mit Unterstützung für Common Language Runtime kompilieren** auf **Keine Common Language Runtime\-Unterstützung** fest.  
  
### So kompilieren Sie eine ausführbare ATL\-Datei mittels \/clr  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften**.  
  
2.  Erweitern Sie im Dialogfeld **Projekteigenschaften** den Knoten neben den **Konfigurationseigenschaften**, und wählen Sie **Allgemein** aus.  Legen Sie im rechten Bereich unter **Projektstandards** die **Common Language Runtime\-Unterstützung** auf **Common Language Runtime\-Unterstützung \(\/clr\)** fest.  
  
3.  Erweitern Sie unter **Konfigurationseigenschaften** den Knoten neben **C\/C\+\+**, und wählen Sie **Allgemein** aus.  Das **Debuginformationsformat** muss auf **Programmdatenbank \/Zi** \(nicht auf **\/ZI**\) festgelegt sein.  
  
4.  Wählen Sie den Knoten **Codegenerierung** aus.  Legen Sie **Minimale Neuerstellung aktivieren** auf **Nein \(\/Gm\-\)** fest.  Legen Sie auch **Vollständige Laufzeitüberprüfungen** auf **Standard** fest.  
  
5.  Wählen Sie unter **Konfigurationseigenschaften** die Option **C\/C\+\+** und dann **Codegenerierung**.  Die **Laufzeitbibliothek** muss entweder auf **Multithreaded\-Debug\-DLL \(\/MDd\)** oder auf **Multithreaded\-DLL \(\/MD\)** festgelegt sein.  
  
6.  Bei allen MIDL\-generierten Dateien \(C\-Dateien\) klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf die entsprechende Datei, und klicken Sie auf **Eigenschaften**.  Erweitern Sie unter **Konfigurationseigenschaften** den Knoten neben **C\/C\+\+**, und wählen Sie **Allgemein** aus.  Legen Sie **Mit Unterstützung für Common Language Runtime kompilieren** auf **Keine Common Language Runtime\-Unterstützung** fest.  
  
### So kompilieren Sie eine ATL\-DLL mittels \/clr  
  
1.  Folgen Sie den Anweisungen unter "So kompilieren Sie eine ausführbare ATL\-Datei mittels \/clr".  
  
2.  Erweitern Sie unter **Konfigurationseigenschaften** den Knoten neben **C\/C\+\+**, und wählen Sie **Vorkompilierte Header** aus.  Legen Sie für **Erstellen\/Verwenden eines vorkompilierten Headers** die Option **Vorkompilierte Header nicht verwenden** fest.  
  
     Klicken Sie alternativ im **Projektmappen\-Explorer** mit der rechten Maustaste auf "Stdafx.cpp", und klicken Sie dann auf **Eigenschaften**.  Erweitern Sie unter **Konfigurationseigenschaften** den Knoten neben **C\/C\+\+**, und wählen Sie **Allgemein** aus.  Legen Sie **Mit Unterstützung für Common Language Runtime kompilieren** auf **Keine Common Language Runtime\-Unterstützung** fest.  
  
3.  Im Falle der DllMain enthaltenden Datei und alle von ihr aufgerufenen Objekte klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf die Datei, und klicken Sie auf **Eigenschaften**.  Erweitern Sie unter **Konfigurationseigenschaften** den Knoten neben **C\/C\+\+**, und wählen Sie **Allgemein** aus.  Legen Sie im rechten Bereich unter **Projektstandards** die Option **Mit Unterstützung für Common Language Runtime kompilieren** auf **Keine Common Language Runtime\-Unterstützung** fest.  
  
## Siehe auch  
 [Gemischte \(systemeigene und verwaltete\) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)