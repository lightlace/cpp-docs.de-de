---
title: Internetsicherheit (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4454eceae2cc5f2e6b46510fe95889c664a568a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348849"
---
# <a name="internet-security-c"></a>Internetsicherheit (C++)
Code-Sicherheit ist ein ernstes Problem für Entwickler und für Benutzer von Internet-Anwendungen. Es sind Risiken: bösartigem Code, Code, der manipulierten und Code von unbekannten Sites oder Autoren.  
  
 Es gibt zwei grundlegende Ansätze für die Sicherheit bei der Entwicklung für das Internet. Die erste heißt "Sandkasten". Bei dieser Vorgehensweise wird eine Anwendung auf einen bestimmten Satz von APIs beschränkt und gefährlich sind z. B. Datei-e/a, in denen ein Programm Daten auf dem Computer eines Benutzers zerstören konnte, ausgeschlossen. Die zweite wird mithilfe von digitalen Signaturen implementiert. Dieser Ansatz wird als "Verpackung" für das Internet bezeichnet. Code wird überprüft, und mithilfe von privaten und öffentlichen Schlüsseln signiert. Bevor der Code ausgeführt wird, wird ihrer digitale Signatur überprüft, um sicherzustellen, dass der Code aus einer bekannten authentifizierte Quelle stammt und der Code nicht geändert wurden, seit sie signiert wurde.  
  
 Im ersten Fall vertrauen Sie, dass die Anwendung wird keine Schaden und Sie den Ursprung der Anwendung vertrauen. Im zweiten Fall sind digitale Signaturen verwendet, damit die Echtheit überprüft wird. Digitale Signatur ist ein dem Branchenstandard verwendet, um zu ermitteln, und geben Sie Details über den Herausgeber des Codes. Die Technologie basiert auf Standards, z. B. RSA und x. 509. Browser zulassen in der Regel Benutzer wählen, ob sie herunterladen und Ausführen von Code Unbekannter Herkunft möchten.  
  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)   
 [Grundlagen der MFC-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)

