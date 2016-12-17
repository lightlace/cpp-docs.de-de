---
title: "Sicherheitsauswirkungen der Anpassung"
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
  - "MFC-Feature Pack, Sicherheit"
  - "Sicherheit, MFC-Feature Pack"
ms.assetid: 9be96b12-be38-43bd-a133-5d671265f7a1
caps.latest.revision: 14
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Sicherheitsauswirkungen der Anpassung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema werden ein potenzielles Sicherheitsrisiko in MFC.  
  
## Mögliche Sicherheits\-Schwäche  
 MFC können den Benutzer Anpassen des Aussehens einer Anwendungsbenutzeroberfläche, beispielsweise, die Darstellung der Schaltflächen und von Symbolen.  MFC unterstützt auch benutzerdefinierte Tools, die den Benutzer Shellbefehle auszuführen.  Eine Sicherheitslücke entsteht, weil die benutzerdefinierten Einstellungen der Anwendung im Benutzerprofil in der Registrierung gespeichert werden.  Jeder, der auf die Registrierung zugreifen kann, kann diese Einstellungen ändern und ändert die Anwendungsdarstellung oder verhalten.  Beispielsweise kann ein Administrator auf dem Computer einen Benutzer imitieren, indem die Anwendung des Benutzers ausgelöst hat, beliebige Programme auszuführen \(sogar einer Netzwerkfreigabe\).  
  
## Problemumgehung  
 Sie sollten alle drei Methoden, die ein in der Registrierung zu schließen:  
  
-   Verschlüsseln Sie die Daten, die dort gespeichert wird  
  
-   Speichern Sie die Daten in einer sicheren Datei nicht in der Registrierung.  
  
     Um eine dieser ersten zwei Methoden zu erreichen, leiten Sie eine Klasse von [CSettingsStore Class](../mfc/reference/csettingsstore-class.md) und überschreiben Sie die Methoden für die Verschlüsselung oder Speicher außerhalb der Registrierung zu implementieren.  
  
-   Sie können Anpassungen in der Anwendung auch deaktivieren.  
  
## Siehe auch  
 [Anpassung für MFC](../mfc/customization-for-mfc.md)