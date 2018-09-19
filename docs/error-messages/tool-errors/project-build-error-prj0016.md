---
title: Projektbuildfehler PRJ0016 | Microsoft-Dokumentation
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
ms.openlocfilehash: c6604bc0bf27b3d0192f602c4df88e5f01e4a161
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135957"
---
# <a name="project-build-error-prj0016"></a>Projektbuildfehler PRJ0016

Sicherheitseinstellungen des Benutzers verhindern, dass den Prozess erstellt werden. Diese Einstellungen sind zum Erstellen erforderlich.

Sie sind als Benutzer angemeldet, die keine Berechtigungen zum Erstellen von Prozessen unter Verwendung eines Prozesses. Sie müssen die Berechtigungsebenen für dieses Benutzerkonto ändern oder wenden Sie sich an den Administrator Ihres Kontos.

Dieser Fehler kann auch auftreten, wenn Sie der folgenden Registrierungsschlüssel festgelegt ist:

\\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun

Löschen Sie den RestrictRun-Schlüssel, um diesen Fehler zu beheben. Wenn dieser Registrierungsschlüssel erforderlich ist, fügen Sie **vcspawn.exe** zur Liste der Einträge im Schlüssel.

Eine weitere Ursache für diesen Fehler ist, dass es sich bei Ihrem richtlinieneinstellung VCSpawn.exe als zulässige Fenster Programm für dieses Benutzerkonto nicht unter dem Registrierungsschlüssel HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun enthalten ist.

Weitere Informationen finden Sie unter:

- Knowledge Base-Artikel 324153, verfügbar auf [ http://support.microsoft.com/default.aspx?scid=kb; En-us; 324153](http://support.microsoft.com/default.aspx?scid=kb;en-us;324153).

- [Einhalten der Systemrichtlinien](https://msdn.microsoft.com/library/aa372139), im Abschnitt "nur zulässig, führen Sie Windows-Anwendungen".