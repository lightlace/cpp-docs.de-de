---
title: Erstellen von Skripts für ATL-Registrierung
ms.date: 05/14/2014
helpviewer_keywords:
- scripting, registry scripting
- ATL, registry
- registrar scripts [ATL]
- scripts, Registrar scripts
- scripts, creating
ms.assetid: cbd5024b-8061-4a71-be65-7fee90374a35
ms.openlocfilehash: f32606701ea08736985f0b0dd2ed82712040a049
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65707060"
---
# <a name="creating-registrar-scripts"></a>Erstellen von Registrierungsskripts

Ein Registrierungsskript bietet datengesteuerten statt API-gesteuertem Zugriff auf die Systemregistrierung. Datengesteuerter Zugriff ist in der Regel effizienter, da nur eine oder zwei Zeilen in einem Skript erforderlich sind, um der Registrierung einen Schlüssel hinzuzufügen.

Der [ATL-Steuerelement-Assistent](../atl/reference/atl-control-wizard.md) generiert automatisch ein Registrierungsskript für Ihren COM-Server. Sie finden dieses Skript in der RGS-Datei, die mit Ihrem Objekt verknüpft ist.

Die Skript-Engine der ATL-Registrierung verarbeitet Ihr Registrierungsskript zur Laufzeit. ATL ruft die Skript-Engine während der Servereinrichtung automatisch auf.

In diesem Artikel werden die folgenden Themen im Zusammenhang mit den Registrierungsskripts behandelt:

- [Einführung in die BNF-Syntax (Backus-Naur-Form)](../atl/understanding-backus-naur-form-bnf-syntax.md)

- [Einführung in Analysestrukturen](../atl/understanding-parse-trees.md)

- [Beispiele für die Registrierungsskripterstellung](../atl/registry-scripting-examples.md)

- [Verwenden von ersetzbaren Parametern (Der Registrierungspräprozessor)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)

- [Aufruf von Skripts](../atl/invoking-scripts.md)

## <a name="see-also"></a>Siehe auch

[Registrierungskomponente (Registrar)](../atl/atl-registry-component-registrar.md)
