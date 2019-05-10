---
title: Wie Benutzerkontensteuerung (UAC) die Anwendung beeinflusst
ms.date: 11/19/2018
helpviewer_keywords:
- UAC [C++]
- security [C++], User Account Control
- user accounts [C++]
- User Account Control [C++]
ms.assetid: 0d001870-253e-4989-b689-f78035953799
ms.openlocfilehash: 3818b0ff7d4e4c551c41726dd44935beb5d32842
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65448474"
---
# <a name="how-user-account-control-uac-affects-your-application"></a>Wie Benutzerkontensteuerung (UAC) die Anwendung beeinflusst

Benutzerkontensteuerung (UAC) ist eine Funktion von Windows Vista, in der Benutzerkonten eingeschränkte Berechtigungen haben. Ausführliche Informationen über UAC finden Sie auf diesen Sites:

- [Developer Best Practices and Guidelines for Applications in einer Umgebung mit geringsten rechten](/windows/desktop/uxguide/winenv-uac)

## <a name="building-projects-after-enabling-uac"></a>Erstellen von Projekten nach der Aktivierung von UAC

Wenn Sie ein Visual Studio erstellen C++ -Projekt auf Windows Vista mit UAC deaktiviert ist, und das später aktiviert, müssen Sie bereinigen und neu erstellen das Projekt, damit es ordnungsgemäß funktioniert.

## <a name="applications-that-require-administrative-privileges"></a>Anwendungen, die Administratorrechte erfordern

Standardmäßig bettet der Visual C++-Linker ein UAC-Fragment in das Manifest einer Anwendung mit der Ausführungsebene `asInvoker`. Wenn die Anwendung für die ordnungsgemäße Ausführung Administratorrechte erfordert (wenn sie z. B. den HKLM-Knoten der Registrierung ändert oder in geschützte Bereiche des Datenträgers wie z. B. das Windows-Verzeichnis schreibt), müssen Sie die Anwendung ändern.

Die erste Möglichkeit besteht, so ändern Sie die UAC-Fragment des Manifests, das Ändern der Ausführungsebene auf *"requireAdministrator"*. Die Anwendung fordert dann den Benutzer vor der Ausführung zur Angabe von Administratorrechten auf. Informationen hierzu finden Sie unter [/MANIFESTUAC (bettet UAC-Informationen in Manifest)](../build/reference/manifestuac-embeds-uac-information-in-manifest.md).

Die zweite Option besteht darin, durch Angabe der `/MANIFESTUAC:NO`-Linkeroption kein UAC-Fragment einzubetten. In diesem Fall wird die Anwendung virtualisiert ausgeführt. Änderungen, die Sie an der Registrierung oder am Dateisystem vornehmen, werden nach Beendigung der Anwendung nicht beibehalten.

Im folgenden Flussdiagramm wird beschrieben, wie die Anwendung abhängig davon ausgeführt wird, ob UAC aktiviert ist und ob die Anwendung ein UAC-Manifest besitzt:

![Windows-Ladeprogramm Verhalten](media/uacflowchart.png "Verhalten der Windows-Ladeprogramm")

## <a name="see-also"></a>Siehe auch

[Empfohlene Vorgehensweisen bezüglich der Sicherheit](security-best-practices-for-cpp.md)
