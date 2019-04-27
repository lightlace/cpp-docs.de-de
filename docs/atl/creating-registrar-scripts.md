---
title: Erstellen von Skripts für ATL-Registrierung
ms.date: 11/04/2016
helpviewer_keywords:
- scripting, registry scripting
- ATL, registry
- registrar scripts [ATL]
- scripts, Registrar scripts
- scripts, creating
ms.assetid: cbd5024b-8061-4a71-be65-7fee90374a35
ms.openlocfilehash: e1a0b66e673fcefd0b75683ef75247a388217361
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250845"
---
# <a name="creating-registrar-scripts"></a>Creating Registrar Scripts

Ein Skript für die Registrierungsstelle bietet datengesteuerten, anstatt API-gesteuert, auf die Registrierung des Systems. Datengesteuerte Zugriff ist in der Regel effizienter, da es nur ein oder zwei Zeilen in einem Skript Hinzufügen eines Schlüssels in der Registrierung kann.

Die [ATL-Steuerelement-Assistent](../atl/reference/atl-control-wizard.md) generiert automatisch ein Skript Registrierungsstelle für Ihren COM-Server. Dieses Skript finden Sie in der RGS-Datei mit dem Objekt verknüpft ist.

Der ATL-Registrierung-Skript-Engine verarbeitet Ihre Registrierungsstelle-Skripts zur Laufzeit. ATL wird automatisch der Skript-Engine während der Server-Setup aufgerufen.

In diesem Artikel werden die folgenden Themen im Zusammenhang mit der Registrierungsstelle Skripts behandelt:

- [Einführung in die BNF-Snytax (Backus Naur Form)](../atl/understanding-backus-nauer-form-bnf-syntax.md)

- [Einführung in Analysestrukturen](../atl/understanding-parse-trees.md)

- [Beispiele für die Registrierungsskripterstellung](../atl/registry-scripting-examples.md)

- [Verwenden von ersetzbaren Parametern (Der Registrierungspräprozessor)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)

- [Aufruf von Skripts](../atl/invoking-scripts.md)

## <a name="see-also"></a>Siehe auch

[Registrierungskomponente (Registrar)](../atl/atl-registry-component-registrar.md)
