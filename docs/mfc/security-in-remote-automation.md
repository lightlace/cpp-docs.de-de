---
title: Sichere Remoteautomatisierung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- AllowRemoteActivation [MFC]
- Remote Automation [MFC], security
- activating objects [MFC]
- security [MFC]
- Automation objects [MFC], security options
- object activation [MFC]
- security [MFC], Remote Automation
ms.assetid: 276b300d-c0b5-4bd8-8bf5-0270994b9cfa
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e535fac6330d6268629e8e3681fec47c7b0d65d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="security-in-remote-automation"></a>Sichere Remoteautomatisierung
Remoteautomatisierung unterstützt ein grundlegendes Verständnis von Sicherheit auf einem Server der Anwendungs-Writer (ändern oder entfernen, sondern Administrator) angeben, wie ein bestimmtes Objekt remote aktiviert werden kann. Alle Automatisierungsobjekte, auf ein vorhandenes System können global, "Remoteaktivierung nicht zulassen" oder "Remoteaktivierung" festgelegt werden. Darüber hinaus und häufiger, können einzelne Objekte solcher Funktionen erteilt werden. Remoteautomatisierung verwendet einen Schlüssel in den registrierungseinstellungen für jedes Objekt, **AllowRemoteActivation**, um zu bestimmen, ob ein angegebener Server Remote aktiviert werden kann. Wenn die systemweiten Einstellungen in diesem Modus verwenden, klicken Sie dann jedes Objekt in der Registrierung zugewiesen sein diesen Schlüssel, und die einzelnen Status jeder einzelnen kann auf "yes" oder "no" entsprechend festgelegt werden.  
  
 Wenn das Server-System Windows NT oder Windows 2000 ausgeführt wird, ist eine alternative Form der Sicherheit zulässig. In diesem Fall verwendet Remoteautomatisierung NT-Zugriffssteuerungsliste (ACL) angeben, welche Benutzer oder Gruppe oder Gruppen von Benutzern Remote auf einen bestimmten Server aktivieren können.  
  
 Beachten Sie, dass die Sicherheitsoptionen für das gesamte Objekt gelten. Es ist nicht möglich, Attribute, die eine bestimmte Schnittstelle oder einzelne Eigenschaften oder Methoden für dieses Objekt festlegen.  
  
 Alle Sicherheitsoptionen können über den Manager Remote Automation-Verbindung (RAC) festgelegt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Remoteautomatisierung](../mfc/remote-automation.md)

