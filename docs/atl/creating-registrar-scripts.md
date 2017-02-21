---
title: "Creating Registrar Scripts | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, Registrierung"
  - "registrar scripts [ATL]"
  - "Erstellen von Skripts, registry scripting"
  - "Skripts, Erstellen"
  - "Skripts, Registrar scripts"
ms.assetid: cbd5024b-8061-4a71-be65-7fee90374a35
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Creating Registrar Scripts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Registrierungsstellenskript stellt datengesteuertes, anstatt API\-angetrieben, Zugriff auf die Systemregistrierung.  Datengesteuerter Zugriff ist in der Regel effizienter, da nur ein oder zwei Anweisungen in einem Skript nachverfolgt, um einen Schlüssel der Registrierung hinzuzufügen.  
  
 [ATL\-Steuerelement\-Assistent](../atl/reference/atl-control-wizard.md) generiert automatisch ein Registrierungsstellenskript für den COM\-Server.  Sie können dieses Skript in der RGS\-Datei suchen, die dem Objekt zugeordnet ist.  
  
 Das Skriptmodul des ATL\-Registrators verarbeitet das Registrierungsstellenskript zur Laufzeit.  ATL wird automatisch das Skriptmodul während der Serverinstallation auf.  
  
 Dieser Artikel enthält folgende Themen, die den Registrierungsstellenskripten verknüpft werden:  
  
-   [Verständnissyntax Backus Naur Formular\-\(BNF\)](../atl/understanding-backus-nauer-form-bnf-syntax.md)  
  
-   [Verständnisanalyse\-Strukturen](../atl/understanding-parse-trees.md)  
  
-   [Registrierungs\-Beispielskripte](../atl/registry-scripting-examples.md)  
  
-   [Verwenden von ersetzbaren Parameter \(der Präprozessor der Registrierungsstelle\)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)  
  
-   [Aufrufen von Skripts](../atl/invoking-scripts.md)  
  
## Siehe auch  
 [Registrierungskomponente \(Registrar\)](../atl/atl-registry-component-registrar.md)