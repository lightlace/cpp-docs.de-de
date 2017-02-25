---
title: "Erstellen des Projekts (ATL-Lernprogramm, Teil 1) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: f6b727d1-390a-4b27-b82f-daadcd9fc059
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Erstellen des Projekts (ATL-Lernprogramm, Teil 1)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Lernprogramm führt Sie schrittweise durch ein nicht attributiertes ATL\-Projekt, durch das ein ActiveX\-Objekt erstellt, das ein Polygon anzeigt.  Das \- Objekt umfasst Optionen für dem Benutzer die Möglichkeit, um die Anzahl der Seiten ändern, die das Polygon und Code bilden, um die Anzeige zu aktualisieren.  
  
> [!NOTE]
>  ATL und MFC ist normalerweise nicht in die Express\-Editionen von Visual Studio unterstützt.  
  
> [!NOTE]
>  Dieses Lernprogramm erstellt den gleichen Quellcode wie das Polygonbeispiel.  Wenn Sie den Quellcode, manuell eingeben vermeiden möchten, können Sie ihn aus [Polygonbeispielzusammenfassung](../top/visual-cpp-samples.md) herunterladen.  Sie können den Polygonquellcode dann verweisen, indem Sie das Lernprogramm arbeiten, oder es verwenden, um für Fehler in Ihrem Projekt zu überprüfen.  
  
### Um das ursprüngliche ATL\-Projekt mit dem ATL\-Projekt\-Assistenten erstellen  
  
1.  In der Visual Studio\-Entwicklungsumgebung auf **Neu** auf dem Menü **Datei** und dann auf **Projekt**.  
  
2.  Klicken Sie auf den Ordner **Visual C\+\+\-Projekte** und wählen Sie **ATL\-Projekt** aus.  
  
3.  Typ `Polygon` als Projektname.  
  
     Der Speicherort für den Quellcode führt in der Regel zu Verzeichnis Eigene Dateien\\Visual Studio Projects, und ein neuer Ordner wird automatisch erstellt.  
  
4.  Sie **OK** und der ATL\-Projekt\-Assistent wird geöffnet.  
  
5.  **Anwendungseinstellungen** auf, um die Optionen zu sehen verfügbar.  
  
6.  Während Sie erstellen, werden ein \- Steuerelement, und ein Steuerelement muss ein prozessinterner Server sein, **Anwendungstyp** als DLL.  
  
7.  Lassen Sie die anderen Optionen an ihren Standardwerten, und klicken Sie auf **Fertig stellen**.  
  
 Der ATL\-Projekt\-Assistent Projekt wird erstellt, indem es mehrere Dateien generiert.  Sie können diese Dateien im Projektmappen\-Explorer anzeigen, indem Sie das Polygonobjekt erweitern.  Die Dateien sind nachfolgend aufgeführt.  
  
|Datei|Beschreibung|  
|-----------|------------------|  
|Polygon.cpp|Enthält die Implementierung von `DllMain`, von `DllCanUnloadNow`, von `DllGetClassObject`, von `DllRegisterServer` und von `DllUnregisterServer`.  Enthält auch die Objektzuordnung, die eine Liste der ATL\-Objekte im Projekt ist.  Dies ist zunächst leer.|  
|Polygon.def|Diese Moduldefinitionsdatei stellt dem Linker mit Informationen über die Exporte, die von der DLL erforderlich sind.|  
|Polygon.idl|Die Interface Definition Language\-Datei, die die Schnittstellen beschrieben, die zu den Objekten spezifisch sind.|  
|Polygon.rgs|Dieses Registrierungsskript enthält Informationen zum Registrieren der DLL des Programms.|  
|Polygon.rc|Die Ressourcendatei, die zuerst die Versionsinformationen und eine Zeichenfolge enthält, die den Projektnamen enthalten.|  
|Resource.h|Die Headerdatei für die Ressourcendatei.|  
|Polygonps.def|Diese Moduldefinitionsdatei stellt dem Linker mit Informationen über die Exporte, die durch den Proxy und Stubden Code Supportanfragen über Apartments erforderlich sind.|  
|stdafx.cpp|Die Datei, die `#include` die ATL\-Implementierungsdateien wird.|  
|stdafx.h|Die Datei, die `#include` der ATL\-Headerdateien wird.|  
  
1.  Klicken Sie im Projektmappen\-Explorer auf das Projekt, `Polygon` mit der rechten Maustaste.  
  
2.  Klicken Sie im Kontextmenü auf **Eigenschaften**.  
  
3.  Klicken Sie auf **Linker**.  Ändern Sie die Option **Pro BenutzerUmleitung** zu **Ja**.  
  
4.  Klicken Sie auf **OK**.  
  
 Im nächsten Schritt fügen Sie ein \- Steuerelement zum Projekt hinzu.  
  
 [Klicken Sie zu Schritt 2](../atl/adding-a-control-atl-tutorial-part-2.md)  
  
## Siehe auch  
 [Lernprogramm](../atl/active-template-library-atl-tutorial.md)