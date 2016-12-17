---
title: "Sichere Remoteautomatisierung"
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
  - "Aktivieren von Objekten"
  - "AllowRemoteActivation"
  - "Automatisierungsobjekte, Sicherheitsoptionen"
  - "Objektaktivierung"
  - "Remoteautomatisierung, Sicherheit"
  - "Sicherheit [MFC]"
  - "Sicherheit [MFC], Remoteautomatisierung"
ms.assetid: 276b300d-c0b5-4bd8-8bf5-0270994b9cfa
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Sichere Remoteautomatisierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Remote\- Automatisierung unterstützt ein grundlegendes Ebene der Sicherheit, um einen Serveranwendungswriter \(oder nicht\) den Administrator zuzulassen wie ein bestimmtes Objekt u remote aktiviert ist.  Alle Automatisierungsobjekte auf einem bestimmten System werden global "unterbinden Remoteaktivierung" festgelegt werden, oder "ermöglichen Sie remote Aktivierung".  Außerdem und häufig, werden einzelne Objekte möglicherweise entsprechende Funktionen zugewiesen.  Remote\- Automatisierung verwendet Schlüssel in den Registrierungseinstellungen jedes Objekts, **AllowRemoteActivation**, ob ein angegebener Servers nicht remote aktiviert ist.  Wenn die systemweiten Einstellungen diesen Modus verwenden, wird jedes Objekt in der Registrierung die Schlüssel zugeordnet werden, und der Status jeder einzelne wird auf "ja" oder "no" entsprechend festgelegt werden.  
  
 Wenn das Serversystem Windows NT oder Windows 2000 ausgeführt wird, wird ein alternatives Formular der Sicherheit ermöglicht.  In diesem Fall verwendet für die Automatisierung NT\-Zugriffssteuerungsliste \(ACL\), um anzugeben, der Benutzer z oder Gruppe oder Benutzergruppen remote einen bestimmten Server aktivieren.  
  
 Beachten Sie, dass die auf Sicherheitsoptionen des gesamten Objekts anwenden; Es ist nicht möglich, Attribute einer bestimmten Schnittstelle oder einzelner Eigenschaften oder Methoden auf diesem Objekt festzulegen.  
  
 Alle Sicherheitsoptionen werden durch den Automatisierungs\-Verbindungs Remote \(rac\)\- Manager festgelegt werden.  
  
## Siehe auch  
 [Remoteautomatisierung](../mfc/remote-automation.md)