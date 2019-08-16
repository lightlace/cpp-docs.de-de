---
title: Wie Benutzerkontensteuerung (UAC) die Anwendung beeinflusst
ms.date: 11/19/2018
helpviewer_keywords:
- UAC [C++]
- security [C++], User Account Control
- user accounts [C++]
- User Account Control [C++]
ms.assetid: 0d001870-253e-4989-b689-f78035953799
ms.openlocfilehash: 8c283e86a71092bb510892b6361f3d0fddc2abb6
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510145"
---
# <a name="how-user-account-control-uac-affects-your-application"></a>Wie Benutzerkontensteuerung (UAC) die Anwendung beeinflusst

Benutzerkontensteuerung (UAC) ist eine Funktion von Windows Vista, in der Benutzerkonten eingeschränkte Berechtigungen haben. Ausführliche Informationen über UAC finden Sie auf diesen Sites:

- [Bewährte Methoden für Entwickler und Richtlinien für Anwendungen in einer Umgebung mit geringsten Rechten](/windows/win32/uxguide/winenv-uac)

## <a name="building-projects-after-enabling-uac"></a>Erstellen von Projekten nach der Aktivierung von UAC

Wenn Sie ein Visual Studio C++ -Projekt unter Windows Vista mit deaktivierter UAC erstellen und Sie später UAC aktivieren, müssen Sie das Projekt bereinigen und neu erstellen, damit es ordnungsgemäß funktioniert.

## <a name="applications-that-require-administrative-privileges"></a>Anwendungen, die Administratorrechte erfordern

Standardmäßig bettet der C++ visuelle Linker ein UAC-Fragment in das Manifest einer Anwendung mit der Ausführungs Ebene `asInvoker`ein. Wenn die Anwendung für die ordnungsgemäße Ausführung Administratorrechte erfordert (wenn sie z. B. den HKLM-Knoten der Registrierung ändert oder in geschützte Bereiche des Datenträgers wie z. B. das Windows-Verzeichnis schreibt), müssen Sie die Anwendung ändern.

Die erste Option besteht darin, das UAC-Fragment des Manifests zu ändern, um die Ausführungs Ebene in " *requilesministrator*" zu ändern. Die Anwendung fordert dann den Benutzer vor der Ausführung zur Angabe von Administratorrechten auf. Weitere Informationen hierzu finden Sie unter [/MANIFESTUAC (bettet UAC-Informationen in Manifest ein)](../build/reference/manifestuac-embeds-uac-information-in-manifest.md).

Die zweite Option besteht darin, durch Angabe der `/MANIFESTUAC:NO`-Linkeroption kein UAC-Fragment einzubetten. In diesem Fall wird die Anwendung virtualisiert ausgeführt. Änderungen, die Sie an der Registrierung oder am Dateisystem vornehmen, werden nach Beendigung der Anwendung nicht beibehalten.

Im folgenden Flussdiagramm wird beschrieben, wie die Anwendung abhängig davon ausgeführt wird, ob UAC aktiviert ist und ob die Anwendung ein UAC-Manifest besitzt:

![Windows-Ladeverhalten](media/uacflowchart.png "Windows-Ladeverhalten")

## <a name="see-also"></a>Siehe auch

[Empfohlene Vorgehensweisen bezüglich der Sicherheit](security-best-practices-for-cpp.md)
