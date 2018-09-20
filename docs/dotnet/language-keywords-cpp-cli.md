---
title: Sprachschlüsselwörter (C++ / CLI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keywords [C++]
ms.assetid: 021013b2-70ac-4df9-aa77-4af1c67a1a67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0b9deb25e203ea805b1430b2ec8e56f17a50123b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445437"
---
# <a name="language-keywords-ccli"></a>Sprachschlüsselwörter (C++/CLI)

Verschiedene Schlüsselwörter, die von Managed Extensions for C++ auf Visual C++ geändert.

In der neuen Visual C++-Syntax wird der doppelte Unterstrich wird als Präfix allen Schlüsselwörtern entfernt (mit einer Ausnahme: `__identifier` beibehalten). Z. B. eine Eigenschaft ist jetzt als deklariert `property`, nicht `__property`.

Es wurden zwei Hauptgründe für die Verwendung der doppelte Unterstrich-Präfix in Managed Extensions:

- Es ist das konforme-Methode für die Bereitstellung von lokale Extensions die ISO-C++-Standard. Ein primäres Ziel von den Entwurf von Managed Extensions bestand darin, Configuration Manager keine Inkompatibilitäten mit der standardmäßigen Sprache, z. B. neue Schlüsselwörter und -Token. Aus diesem Grund war größtenteils, die die Auswahl der Zeigersyntax für die Deklaration von Objekten, die von verwalteten Verweistypen motiviert.

- Die Verwendung doppelter Unterstriche, abgesehen von seiner Konformitätsaspekt, ist auch nicht-invasive mit der der Benutzer der Sprache der vorhandenen Codebasis wird garantiert. Dies war eine zweite Hauptziel von Managed Extensions-Design.

Trotz entfernen die doppelten unterstrichen, weiterhin Microsoft Standardkonformität. Allerdings unterstützt, für die dynamische CLR-Objektmodell ein neues, leistungsstarkes Programmierparadigma darstellt. Unterstützung für dieses neue Paradigma ist erforderlich, einen eigenen allgemeinen Schlüsselwörter und Token. Wir haben haben versucht, einen erstklassigen Ausdruck dieses neue Paradigma bei der Integration und Unterstützung der standardmäßigen Sprache anzugeben. Das neue Syntaxdesign stellt eine erstklassige Programmierung dieser zwei unterschiedliche Objektmodelle bereit.

Auf ähnliche Weise können wir mit die nicht-invasive Art der diese neuen Programmiersprachen-Schlüsselworten maximieren. Dies wurde mit der Verwendung von kontextbezogener und durch Leerzeichen getrennten Schlüsselwörtern erreicht. Bevor wir die neue Syntax betrachten, probieren Sie zu der diese zwei Arten von spezielle Schlüsselwort sinnvoll.

Ein kontextbezogenes Schlüsselwort ist in bestimmten Programmkontext eine besondere Bedeutung. Im allgemeinen Programm, z. B. `sealed` wird als ein normaler Bezeichner behandelt. Allerdings tritt in der Deklarationsteil eines Klassentyps verwaltete Referenz zur, wird es als ein Schlüsselwort im Rahmen der Deklaration dieser Klasse behandelt. Dies minimiert mögliche Nebenwirkungen durch die Einführung von etwas ein neues Schlüsselwort in der Sprache, die unserer Meinung nach ist sehr wichtig für Benutzer mit einer vorhandenen Codebasis. Zur gleichen Zeit ermöglicht es die neuen Funktionen zu eine erstklassige Erfahrung von zusätzlichen Sprachfeatures - etwas zu haben, die nicht mit Managed Extentions möglich. Ein Beispiel dafür, wie `sealed` wird verwendet, finden Sie unter [Deklaration eines verwalteten Klassentyps](../dotnet/declaration-of-a-managed-class-type.md).

Eine durch Leerzeichen getrennten-Schlüsselwort, z. B. `value class`, ist ein Sonderfall, der ein kontextbezogenes Schlüsselwort. Sie verbindet eine existing-Schlüsselwort mit einem kontextbezogene Modifizierer, die durch ein Leerzeichen getrennt. Das Paar wird nicht als zwei getrennte Schlüsselwörter, sondern als einzelne Einheit behandelt.

## <a name="see-also"></a>Siehe auch

[Einführung in die C++/CLI-Migration](../dotnet/cpp-cli-migration-primer.md)<br/>
[Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)