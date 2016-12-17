---
title: "Neuverteilen von Visual&#160;C++ ActiveX-Steuerelementen"
ms.custom: na
ms.date: "12/03/2016"
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
  - "Steuerelemente [C++], Verteilen"
  - "Steuerelemente [C++], Verteilen"
ms.assetid: eefbb7e4-d28c-4c35-98bf-d9540cfaae83
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# Neuverteilen von Visual&#160;C++ ActiveX-Steuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 6.0 bietet ActiveX\-Steuerelemente zur Verwendung in Anwendungen, die Sie weiterverteilen können.  Diese Steuerelemente sind nicht mehr in Visual C\+\+ enthalten.  Gemäß den für Visual C\+\+ 6.0 geltenden Lizenzverträgen können Sie diese Steuerelemente jedoch zusammen mit in Visual C\+\+ entwickelten Anwendungen weiterverteilen.  
  
> [!NOTE]
>  Visual C\+\+ 6.0 wird von Microsoft nicht länger unterstützt.  
  
 Eine Liste der verteilbaren, in Visual C\+\+ 6.0 enthaltenen ActiveX\-Steuerelemente finden Sie unter **Common\\Redist\\Redist.txt** auf CD 1 der Produkt\-CDs von Visual C\+\+ 6.0.  
  
 Beim Verteilen von Anwendungen müssen Sie mithilfe von Regsvr32.exe die OCX\-Datei für das ActiveX\-Steuerelement installieren und registrieren.  Zudem sollten Sie sicherstellen, dass auf dem Zielcomputer aktuelle Versionen der folgenden Systemdateien vorhanden sind \(ein Sternchen zeigt an, dass die Datei registriert werden muss\):  
  
-   Asycfilt.dll  
  
-   Comcat.dll \*  
  
-   Oleaut32.dll \*  
  
-   Olepro32.dll \*  
  
-   Stdole2.tlb  
  
 Falls diese DLLs im Zielsystem nicht verfügbar sind, müssen Sie sie mithilfe des vorgeschriebenen Mechanismus für die Aktualisierung des entsprechenden Betriebssystems aktualisieren.  Die aktuellen Service Packs für Windows\-Betriebssysteme können Sie unter [http:\/\/www.update.microsoft.com\/microsoftupdate\/v6\/vistadefault.aspx?ln\=de\-de](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=de-de) herunterladen.  
  
 Wenn in der Anwendung ein ActiveX\-Steuerelement zum Herstellen einer Verbindung mit einer Datenbank verwendet wird, muss Microsoft Data Access Components \(MDAC\) auf dem Zielsystem installiert sein.  Weitere Informationen finden Sie unter [Neuverteilen von Datenbankunterstützungsdateien](../ide/redistributing-database-support-files.md).  
  
 Bei Verwendung eines ActiveX\-Steuerelements, über das eine Datenbankverbindung hergestellt wird, müssen Sie außerdem den Datenquellennamen auf dem Zielcomputer replizieren.  Dieser Vorgang kann programmgesteuert mit Funktionen wie `ConfigDSN` ausgeführt werden.  
  
 Manche verteilbaren ActiveX\-Steuerelemente weisen zusätzliche Abhängigkeiten auf.  Für jede OCX\-Datei im Ordner **Os\\System** auf der Visual C\+\+ 6.0\-Produkt\-CD ist auch eine DEP\-Datei vorhanden.  Durchsuchen Sie für jede OCX\-Datei, die Sie weiterverteilen möchten, die entsprechende DEP\-Datei nach einem oder mehreren USES\-Einträgen.  Falls eine Datei aufgeführt wird, muss diese auf dem Zielcomputer vorhanden sein.  Alle DLLs, die direkt eine OCX\-Datei unterstützen, müssen registriert werden.  \(Damit **Regsvr32.exe** erfolgreich ausgeführt werden kann, müssen auf dem Zielcomputer zunächst alle DLLs enthalten sein, die das Steuerelement statisch lädt.\) Wenn zudem für eine als Abhängigkeit aufgeführte DLL auch eine DEP\-Datei im Ordner Os\\System der Visual C\+\+ 6.0\-CD vorhanden ist, müssen Sie auch diese DEP\-Datei auf USES\-Einträge überprüfen.  
  
## Siehe auch  
 [Verteilen von Visual C\+\+\-Dateien](../ide/redistributing-visual-cpp-files.md)