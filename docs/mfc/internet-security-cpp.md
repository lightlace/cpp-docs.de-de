---
title: Internetsicherheit (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- code signing [MFC], Internet security
- sandboxing [MFC]
- digital signatures [MFC], Internet security
- code signing [MFC]
- Web application security [MFC]
- code access security [MFC], Internet security considerations
- security [MFC]
- security [MFC], Internet
- Internet applications [MFC], security
- Web application security [MFC], Internet security approaches
ms.assetid: bf0da697-81bc-41f0-83fa-d7f82ed83df8
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1a44e528e871d784c432730799c44ac91af465be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="internet-security-c"></a>Internetsicherheit (C++)
Code-Sicherheit ist ein ernstes Problem für Entwickler und für Benutzer von Internet-Anwendungen. Es sind Risiken: bösartigem Code, Code, der manipulierten und Code von unbekannten Sites oder Autoren.  
  
 Es gibt zwei grundlegende Ansätze für die Sicherheit bei der Entwicklung für das Internet. Die erste heißt "Sandkasten". Bei dieser Vorgehensweise wird eine Anwendung auf einen bestimmten Satz von APIs beschränkt und gefährlich sind z. B. Datei-e/a, in denen ein Programm Daten auf dem Computer eines Benutzers zerstören konnte, ausgeschlossen. Die zweite wird mithilfe von digitalen Signaturen implementiert. Dieser Ansatz wird als "Verpackung" für das Internet bezeichnet. Code wird überprüft, und mithilfe von privaten und öffentlichen Schlüsseln signiert. Bevor der Code ausgeführt wird, wird ihrer digitale Signatur überprüft, um sicherzustellen, dass der Code aus einer bekannten authentifizierte Quelle stammt und der Code nicht geändert wurden, seit sie signiert wurde.  
  
 Im ersten Fall vertrauen Sie, dass die Anwendung wird keine Schaden und Sie den Ursprung der Anwendung vertrauen. Im zweiten Fall sind digitale Signaturen verwendet, damit die Echtheit überprüft wird. Digitale Signatur ist ein dem Branchenstandard verwendet, um zu ermitteln, und geben Sie Details über den Herausgeber des Codes. Die Technologie basiert auf Standards, z. B. RSA und x. 509. Browser zulassen in der Regel Benutzer wählen, ob sie herunterladen und Ausführen von Code Unbekannter Herkunft möchten.  
  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)   
 [Grundlagen der MFC-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)

