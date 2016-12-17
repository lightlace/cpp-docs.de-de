---
title: "Standardm&#228;&#223;ige ATL-Projektkonfigurationen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Projekte, Standardkonfigurationen"
ms.assetid: 7e272722-41af-4330-b965-a6d74ec16880
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Standardm&#228;&#223;ige ATL-Projektkonfigurationen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema werden die standardmäßigen Projektkonfigurationen in Visual C\+\+ .NET und die standardmäßigen Projektkonfigurationen in Visual C\+\+ 6.0 miteinander verglichen.  
  
## Standardkonfigurationen in Visual C\+\+ .NET  
 In Visual C\+\+ .NET erstellt der ATL\-Projekt\-Assistent standardmäßig zwei Projektkonfigurationen.  
  
### Visual C\+\+ .NET\-Konfigurationen  
  
|Konfiguration|Zeichensatz|Verwendung von ATL|  
|-------------------|-----------------|------------------------|  
|Release|MBCS|DLL|  
|Debug|MBCS|DLL|  
  
 **Zeichensatz** und **Verwendung von ATL** können im Dialogfeld **Projekteinstellungen** auf der Registerkarte **Allgemein** geändert werden.  Anhand des Konfigurations\-Managers können Sie auch eigene Konfigurationen hinzufügen.  Details zu diesen Thema finden Sie unter [Buildkonfigurationen](../Topic/Understanding%20Build%20Configurations.md).  
  
## Standardkonfigurationen in Version 6.0  
 In Visual C\+\+ 6.0 erstellte der ATL COM\-Anwendungs\-Assistent \(jetzt als ATL\-Projekt\-Assistent bezeichnet\) standardmäßig sechs Projektkonfigurationen.  Die Konfigurationen waren Varianten von Release, Debug, Unicode, Verwendung von CRT und ATL\-Einstellungen.  All diese Konfigurationen können in Visual C\+\+ .NET bei Bedarf mit dem Konfigurations\-Manager dupliziert werden.  
  
### Version 6.0\-Konfigurationen  
  
|Konfiguration|Zeichensatz|Verwendung von ATL|  
|-------------------|-----------------|------------------------|  
|Debug|MBCS|Static|  
|Debug Unicode|UNICODE|Static|  
|Release Min Dependency|MBCS|Static|  
|Release Min Dependency Unicode|UNICODE|Static|  
|Release Min Size|MBCS|DLL|  
|Release Min Size Unicode|UNICODE|DLL|  
  
## Siehe auch  
 [Programmieren mit ATL\- und C\-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md)   
 [Configuration Manager Dialog Box](assetId:///fa182dca-282e-4ae5-bf37-e155344ca18b)   
 [Anwendungen in Visual Studio erstellen](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md)