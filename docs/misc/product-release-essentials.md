---
title: "Grundlagen zu Produktversionen"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "Bereitstellung, Grundlagen"
  - "Installation [Visual Studio SDK], Grundlagen"
ms.assetid: 28370bc8-f3a7-4c5e-9b35-8331cda14ff4
caps.latest.revision: 12
caps.handback.revision: "12"
manager: "douge"
---
# Grundlagen zu Produktversionen
Ein angenehmes und stabiles Setuperlebnis hinterlässt in den Köpfen der Benutzer einen bleibenden Eindruck hinsichtlich Ihres [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-Integrationsprodukts. Ein unangenehmes Setuperlebnis hinterlässt ebenfalls einen bleibenden Eindruck, daher stellt das Befolgen bewährter Methoden beim Entwickeln und Testen des Setups einen lohnenden Aufwand dar.  
  
## Entwickeln von Setuppaketen für Windows Installer  
 Windows Installer ist der empfohlene Installations\- und Konfigurationsdienst für Windows und für [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-Integrationsprodukte.  
  
> [!NOTE]
>  Die [!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)]\-Dokumentation zur Installation von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-Integrationsprodukten baut auf Windows Installer\-Konzepten auf, behandelt Windows Installer aber nicht selbst. Links zu relevanten Abschnitten der Windows Installer\-Dokumentation finden Sie in der folgenden Tabelle.  
  
 Im Setupkontext bezieht sich *Komponente* auf eine Windows Installer\-Komponente. Komponenten enthalten Ressourcen wie Dateien und Registrierungseinträge und werden als Einheit installiert und entfernt.  
  
|Aufgabe|Weitere Informationen finden Sie unter|  
|-------------|--------------------------------------------|  
|Weitere Informationen zu Windows Installer.|[Windows Installer](http://msdn.microsoft.com/library/aa372866.aspx)|  
|Ermitteln Sie Ihre Systemanforderungen für VSPackage.|-   [Ermitteln von Systemanforderungen](../Topic/Detecting%20System%20Requirements.md)|  
|Erfahren Sie, wie Sie ein VSPackage in einem Setuppaket registrieren.|-   [VSPackage\-Registrierung](../Topic/VSPackage%20Registration.md)<br />-   [Befehle, die nach der Installation ausgeführt werden müssen](../Topic/Commands%20That%20Must%20Be%20Run%20After%20Installation.md)|  
|Weitere Informationen erhalten Sie in einem Installationspaketbeispiel.|-   Setupbeispiel zur IronPython\-Integration|  
  
## Unterstützung von parallelen Produkten  
 „Parallel“ \(manchmal auch als *SxS* bezeichnet\) bezieht sich auf die Fähigkeit, mehrere Versionen desselben Produkts parallel installieren und sogar gleichzeitig ausführen zu können. Für [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-Integrationsprodukte bezieht sich dieser Begriff auch auf die Tatsache, dass die parallele Ausführung von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] selbst unterstützt wird.  
  
|Aufgabe|Weitere Informationen finden Sie unter|  
|-------------|--------------------------------------------|  
|Erhalten Sie weitere Informationen zur Unterstützung von mehreren Versionen von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] in Ihrem [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-Integrationsprodukt.|-   [Auswählen zwischen freigegebenen und versioniert VSPackages](../Topic/Choosing%20Between%20Shared%20and%20Versioned%20VSPackages.md)<br />-   [Verwaltung von Komponenten](../Topic/Component%20Management.md)|  
|Erhalten Sie weitere Informationen zur Unterstützung Ihres [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-Integrationsprodukts.|-   [Auswählen zwischen freigegebenen und versioniert VSPackages](../Topic/Choosing%20Between%20Shared%20and%20Versioned%20VSPackages.md)<br />-   [Registrieren von Dateinamenerweiterungen für Seite\-an\-Seite\-Installationen](../Topic/Registering%20File%20Name%20Extensions%20for%20Side-By-Side%20Deployments.md)<br />-   [Ermitteln von Systemanforderungen](../Topic/Detecting%20System%20Requirements.md)<br />-   [Befehle, die nach der Installation ausgeführt werden müssen](../Topic/Commands%20That%20Must%20Be%20Run%20After%20Installation.md)|  
  
## Testen Ihres Visual Studio\-Integrationsprodukts  
 Die [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-VSIT\-Suite \(Visual Studio Integration Test\) umfasst eine Reihe von Tests, mit denen überprüft wird, ob ein VSPackage ordnungsgemäß in [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] integriert wurde. VSIT testet keine VSPackage\-Funktionen, hilft aber dabei sicherzustellen, dass ein VSPackage keine anderen [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-Funktionen beeinträchtigt. Weitere Informationen finden Sie unter [Visual Studio\-Integrationstests](assetId:///8d741735-7d93-46c2-ab93-01da7a0e016d).