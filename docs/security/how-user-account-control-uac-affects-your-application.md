---
title: Wie Benutzerkontensteuerung (UAC) die Anwendung beeinflusst
ms.date: 11/19/2018
helpviewer_keywords:
- UAC [C++]
- security [C++], User Account Control
- user accounts [C++]
- User Account Control [C++]
ms.assetid: 0d001870-253e-4989-b689-f78035953799
ms.openlocfilehash: 3702462ec892025cfb4f24d9c91e6db705b1b9a5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179242"
---
# <a name="how-user-account-control-uac-affects-your-application"></a>Wie Benutzerkontensteuerung (UAC) die Anwendung beeinflusst

Benutzerkontensteuerung (UAC) ist eine Funktion von Windows Vista, in der Benutzerkonten eingeschränkte Berechtigungen haben. Ausführliche Informationen über UAC finden Sie auf diesen Sites:

- [Developer Best Practices and Guidelines for Applications in einer Umgebung mit geringsten rechten](/windows/desktop/uxguide/winenv-uac)

## <a name="building-projects-after-enabling-uac"></a>Erstellen von Projekten nach der Aktivierung von UAC

Wenn Sie ein Visual C++-Projekt unter Windows Vista erstellen, UAC bei der Erstellung deaktiviert ist und später aktiviert wird, müssen Sie das Projekt bereinigen und erneut erstellen, damit es ordnungsgemäß funktioniert.

## <a name="applications-that-require-administrative-privileges"></a>Anwendungen, die Administratorrechte erfordern

Standardmäßig bettet der Visual C++-Linker ein UAC-Fragment in das Manifest einer Anwendung mit der Ausführungsebene `asInvoker`. Wenn die Anwendung für die ordnungsgemäße Ausführung Administratorrechte erfordert (wenn sie z. B. den HKLM-Knoten der Registrierung ändert oder in geschützte Bereiche des Datenträgers wie z. B. das Windows-Verzeichnis schreibt), müssen Sie die Anwendung ändern.

Die erste Möglichkeit besteht, so ändern Sie die UAC-Fragment des Manifests, das Ändern der Ausführungsebene auf *"requireAdministrator"*. Die Anwendung fordert dann den Benutzer vor der Ausführung zur Angabe von Administratorrechten auf. Informationen hierzu finden Sie unter [/MANIFESTUAC (bettet UAC-Informationen in Manifest)](../build/reference/manifestuac-embeds-uac-information-in-manifest.md).

Die zweite Option besteht darin, durch Angabe der `/MANIFESTUAC:NO`-Linkeroption kein UAC-Fragment einzubetten. In diesem Fall wird die Anwendung virtualisiert ausgeführt. Änderungen, die Sie an der Registrierung oder am Dateisystem vornehmen, werden nach Beendigung der Anwendung nicht beibehalten.

Im folgenden Flussdiagramm wird beschrieben, wie die Anwendung abhängig davon ausgeführt wird, ob UAC aktiviert ist und ob die Anwendung ein UAC-Manifest besitzt:

![Windows-Ladeprogramm Verhalten](media/uacflowchart.png "Verhalten der Windows-Ladeprogramm")

## <a name="see-also"></a>Siehe auch

[Empfohlene Vorgehensweisen bezüglich der Sicherheit](security-best-practices-for-cpp.md)
