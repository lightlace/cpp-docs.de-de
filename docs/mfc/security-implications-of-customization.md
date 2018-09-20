---
title: Sicherheitsauswirkungen der Anpassung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- security, MFC Feature Pack
- MFC Feature Pack, security
ms.assetid: 9be96b12-be38-43bd-a133-5d671265f7a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 876f3b45cc9f45ab5ff1aaa7e07116482f89afc1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442083"
---
# <a name="security-implications-of-customization"></a>Sicherheitsauswirkungen der Anpassung

In diesem Thema wird erläutert, eine potenzielle Sicherheitslücke in MFC.

## <a name="potential-security-weakness"></a>Potenzielle Sicherheitsrisiko

MFC ermöglicht dem Benutzer das Anpassen des Layouts der Benutzeroberfläche einer Anwendung, z. B. die Darstellung der Schaltflächen und Symbole. MFC unterstützt auch benutzerdefinierte Tools, die der Benutzer, die Shellbefehle ausführen können. Ein Sicherheitsrisiko tritt auf, da die angepassten Einstellungen der Anwendung im Benutzerprofil in der Registrierung gespeichert werden. Jeder, die Registrierung zugreifen kann, kann diese Einstellungen bearbeiten und ändern die Darstellung der Anwendung oder das Verhalten. Beispielsweise kann ein Administrator auf dem Computer Identität eines Benutzers anzunehmen durch Anwendung des Benutzers zum Ausführen beliebiger Software (auch von einer Netzwerkfreigabe) verursacht.

## <a name="workarounds"></a>Problemumgehung

Es wird empfohlen, diese drei verschiedene Arten, um die Sicherheitsrisiken in der Registrierung zu schließen:

- Verschlüsseln der Daten, die dort gespeichert ist

- Store die Daten in einer sicheren Datei statt in der Registrierung.

     Um diese zunächst zwei unterschiedliche Arten zu erreichen, leiten Sie eine Klasse von [CSettingsStore-Klasse](../mfc/reference/csettingsstore-class.md) und überschreiben Sie die Methoden zum Implementieren der Verschlüsselung oder Speicher außerhalb der Registrierung.

- Sie können auch Anpassungen in Ihrer Anwendung deaktivieren.

## <a name="see-also"></a>Siehe auch

[Anpassung für MFC](../mfc/customization-for-mfc.md)

