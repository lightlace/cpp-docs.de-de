---
title: Sicherheitsauswirkungen der Anpassung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- security, MFC Feature Pack
- MFC Feature Pack, security
ms.assetid: 9be96b12-be38-43bd-a133-5d671265f7a1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b408b4595e95016323d2b43f1ed51fc6e2e6d244
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="security-implications-of-customization"></a>Sicherheitsauswirkungen der Anpassung
In diesem Thema wird erläutert, ein potenzielles Sicherheitsrisiko in MFC.  
  
## <a name="potential-security-weakness"></a>Potenzielle Sicherheitslücke  
 MFC ermöglicht es dem Benutzer das Aussehen der Benutzeroberfläche einer Anwendung, z. B. die Darstellung von Schaltflächen und Symbole anpassen. MFC unterstützt auch benutzerdefinierte Tools, die der Benutzer mit dem Shellbefehle ausführen können. Ein Sicherheitsrisiko tritt auf, da die angepassten Einstellungen der Anwendung im Benutzerprofil in der Registrierung gespeichert sind. Jemand auf die Registrierung zugreifen kann kann diese Einstellungen bearbeiten und ändern Sie die Anwendung Darstellung oder Verhalten. Beispielsweise könnte ein Administrator auf dem Computer Identität eines Benutzers anzunehmen durch die Anwendung des Benutzers zum Ausführen beliebiger Programme (auch über eine Netzwerkfreigabe) verursacht.  
  
## <a name="workarounds"></a>Problemumgehung  
 Es wird empfohlen, alle diese drei Methoden zum Schließen von Sicherheitsrisiken in der Registrierung:  
  
-   Verschlüsseln der Daten, die es gespeichert ist  
  
-   Speichern Sie die Daten in einer sicheren Datei statt in der Registrierung.  
  
     Um dieser ersten beiden Arten zu erreichen, leiten Sie eine Klasse von [CSettingsStore-Klasse](../mfc/reference/csettingsstore-class.md) und überschreiben Sie die Methoden zum Implementieren von Verschlüsselung oder Speicher außerhalb der Registrierung.  
  
-   Sie können auch die Anpassungen in Ihrer Anwendung deaktivieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Anpassung für MFC](../mfc/customization-for-mfc.md)

