---
title: Projektbuildfehler PRJ0016
ms.date: 11/04/2016
f1_keywords:
- PRJ0016
helpviewer_keywords:
- PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
ms.openlocfilehash: 6733ef1f390f2ff377356dda3f7cd3ebfe10cc2b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509880"
---
# <a name="project-build-error-prj0016"></a>Projektbuildfehler PRJ0016

Die Sicherheitseinstellungen des Benutzers verhindern, dass der Prozess erstellt wird. Diese Einstellungen sind zum entwickeln erforderlich.

Sie sind als Benutzer angemeldet, der nicht über die Berechtigung zum Erstellen von Prozessen mit einem Prozess verfügt. Sie müssen die Berechtigungsstufen für dieses Benutzerkonto ändern oder Ihren Konto Administrator kontaktieren.

Dieser Fehler kann auch auftreten, wenn der folgende Registrierungsschlüssel festgelegt ist:

\\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun

Löschen Sie den Schlüssel RestrictRun, um diesen Fehler zu beheben. Wenn dieser Registrierungsschlüssel benötigt wird, fügen Sie " **vcspawn. exe** " an die Liste der Einträge im Schlüssel an.

Eine weitere Ursache für diesen Fehler besteht darin, dass die Richtlinien Einstellung "VCSPAWN. exe" nicht unter dem Registrierungsschlüssel HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun als zulässiges Fensterprogramm für dieses Benutzerkonto enthält.

Weitere Informationen finden Sie unter [einhalten von System Richtlinien Einstellungen](/previous-versions/windows/desktop/Policy/adhering-to-system-policy-settings)im Abschnitt "nur zulässige Windows-Anwendungen ausführen".