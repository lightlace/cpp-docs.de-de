---
title: "Projektvorlage f&#252;r WRL-Klassenbibliothek | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 628b0852-89e5-44f8-bf58-a09762bda15c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Projektvorlage f&#252;r WRL-Klassenbibliothek
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie Visual Studio verwenden, um ein [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) zu schreiben, können Sie die Aufgabe erheblich vereinfachen, indem Sie die WRL\-Klassenbibliotheksprojektvorlage herunterladen.  
  
> [!NOTE]
>  Wenn Sie die Projekteinstellungen für ein vorhandenes Projekt manuell aktualisieren müssen, Sie finden [DLLs \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh699881\(v=vs.110\).aspx).  
  
## Laden Sie die WRL\-Projektvorlage herunter  
 Visual Studio stellt eine Vorlage nicht für [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\-Projekte.  Im Folgenden wird gezeigt, wie eine Projektvorlage herunterladen, die eine Grundkursbibliothek für [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] \- Apps mit [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] veranschaulicht.  
  
#### Um die WRL\-Projektvorlage herunterladen  
  
1.  Wählen Sie auf der Menüleiste **Datei**, **Neues Projekt** aus.  
  
2.  Im linken Bereich des Dialogfelds **Neues Projekt**, wählen Sie **Online** und wählen Sie dann **Vorlagen** aus.  
  
3.  Im Feld **Onlinevorlagen durchsuchen** in der rechten oberen Ecke, geben Sie `WRL-Klassenbibliothek` ein.  Wenn die Vorlage in den Suchergebnissen angezeigt wird, wählen Sie die Schaltfläche **OK** aus.  
  
4.  Im Dialogfeld **Herunterladen und installieren** wenn Sie den Lizenzbedingungen zustimmen, wählen Sie die Schaltfläche **Installieren** aus.  
  
5.  Nachdem die Vorlage installiert, erstellen Sie ein Projekt, indem Sie **Datei** auswählen, **Neues Projekt**, und wählen die Vorlage. `WRLClassLibrary` Das Projekt erstellt eine DLL.  
  
## Beispiele, die die Bereitstellung verwenden  
 Lesen Sie unter [Exemplarische Vorgehensweise: Erstellen einer Basiskomponente für Windows\-Runtime](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md) finden Sie ein Beispiel, das diese Vorlage verwendet, um eine [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] Komponente zu erstellen.  
  
## Was die Projektvorlage stellt  
 Die Projektvorlage stellt bereit:  
  
-   eine IDL\-Datei, die die MIDL\-Attribute für eine einfache Schnittstelle die Klassenimplementierung deklariert.  Im Folgenden ein Beispiel:  
  
     [!CODE [wrl-project-template#1](../CodeSnippet/VS_Snippets_Misc/wrl-project-template#1)]  
  
-   einer CPP\-Datei, die die Klassenimplementierung definiert.  Im Folgenden ein Beispiel:  
  
     [!CODE [wrl-project-template#2](../CodeSnippet/VS_Snippets_Misc/wrl-project-template#2)]  
  
     Die [RuntimeClass](../windows/runtimeclass-class.md) Basisklassenhilfen verwalten den globalen Verweis aller Objekte im Modul und deklarieren die Methoden der Schnittstellen [IUnknown](assetId:///33f1d79a-33fc-4ce5-a372-e08bda378332) und [IInspectable](assetId:///0657e51f-d4c0-46c6-927d-b01e54b6846c).  Das [InspectableClass](../windows/inspectableclass-macro.md)\-Makro implementiert `IUnknown` und `IInspectable`.  Das Makro [ActivatableClass](../windows/activatableclass-macros.md) stellt eine Klassenfactory erstellt, die Instanzen der Klasse erstellt.  
  
-   eine Datei mit dem Namen module.cpp, das die Bibliotheksexporte `DllMain`, `DllCanUnloadNow`, `DllGetActivationFactory` und `DllGetClassObject` definiert.  
  
## Siehe auch  
 [Windows Runtime C\+\+ Template Library \(WRL\)](../windows/windows-runtime-cpp-template-library-wrl.md)