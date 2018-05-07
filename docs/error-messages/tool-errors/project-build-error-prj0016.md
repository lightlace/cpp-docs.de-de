---
title: Projektbuildfehler PRJ0016 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0016
dev_langs:
- C++
helpviewer_keywords:
- PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6184e5bb251a2b74e8500cc195a38f2d814c1b5f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0016"></a>Projektbuildfehler PRJ0016
Sicherheitseinstellungen für den Benutzer verhindern, dass der Prozess erstellt wird. Diese Einstellungen sind zum Erstellen von erforderlich.  
  
 Sie sind als Benutzer angemeldet, die nicht über Berechtigungen zum Erstellen von Prozessen, die mit einem Prozess verfügt. Sie müssen die Berechtigungsebenen für dieses Benutzerkonto ändern, oder wenden Sie sich an den Administrator Ihres Kontos.  
  
 Dieser Fehler kann auch auftreten, wenn Sie der folgenden Registrierungsschlüssel festgelegt ist:  
  
 \\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun  
  
 Um diesen Fehler zu beheben, löschen Sie den RestrictRun-Schlüssel. Wenn dieser Registrierungsschlüssel benötigt wird, hängen Sie **vcspawn.exe** zur Liste der Einträge im Schlüssel.  
  
 Eine weitere Ursache für diesen Fehler ist, dass die Einstellung Ihrer VCSpawn.exe als zulässige Fenster Programm für dieses Benutzerkonto nicht unter dem Registrierungsschlüssel HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun enthalten ist.  
  
 Weitere Informationen finden Sie unter:  
  
-   Knowledge Base-Artikel 324153, verfügbar auf [ http://support.microsoft.com/default.aspx?scid=kb; En-us; 324153](http://support.microsoft.com/default.aspx?scid=kb;en-us;324153).  
  
-   [Systemeinstellungen für die Richtlinie einhalten](http://msdn.microsoft.com/library/aa372139), im Abschnitt "nur dann zulässig, führen Sie Windows-Anwendungen".