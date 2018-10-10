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
ms.openlocfilehash: ceb004cba243d6e2e9c44aadcaa40670ef7a0bbb
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890256"
---
# <a name="project-build-error-prj0016"></a>Projektbuildfehler PRJ0016

Sicherheitseinstellungen des Benutzers verhindern, dass den Prozess erstellt werden. Diese Einstellungen sind zum Erstellen erforderlich.

Sie sind als Benutzer angemeldet, die keine Berechtigungen zum Erstellen von Prozessen unter Verwendung eines Prozesses. Sie müssen die Berechtigungsebenen für dieses Benutzerkonto ändern oder wenden Sie sich an den Administrator Ihres Kontos.

Dieser Fehler kann auch auftreten, wenn Sie der folgenden Registrierungsschlüssel festgelegt ist:

\\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun

Löschen Sie den RestrictRun-Schlüssel, um diesen Fehler zu beheben. Wenn dieser Registrierungsschlüssel erforderlich ist, fügen Sie **vcspawn.exe** zur Liste der Einträge im Schlüssel.

Eine weitere Ursache für diesen Fehler ist, dass es sich bei Ihrem richtlinieneinstellung VCSpawn.exe als zulässige Fenster Programm für dieses Benutzerkonto nicht unter dem Registrierungsschlüssel HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun enthalten ist.

Weitere Informationen finden Sie unter [Systemrichtlinieneinstellungen Einhaltung](https://msdn.microsoft.com/library/aa372139), im Abschnitt "nur zulässig, führen Sie Windows-Anwendungen".