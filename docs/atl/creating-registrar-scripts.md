---
title: Erstellen von Skripts für ATL-Registrierung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- scripting, registry scripting
- ATL, registry
- registrar scripts [ATL]
- scripts, Registrar scripts
- scripts, creating
ms.assetid: cbd5024b-8061-4a71-be65-7fee90374a35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e140e66ee24d8333d25c0c2942924c7a9db4965b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="creating-registrar-scripts"></a>Creating Registrar Scripts
Ein Skript für die Registrierungsstelle stellt eines datengesteuerten, anstatt API-driven, Zugriff auf die Registrierung bereit. Datengesteuerte Zugriff ist in der Regel effizienter, da nur ein oder zwei Zeilen in einem Skript dauert, einen Schlüssel zur Registrierung hinzuzufügen.  
  
 Die [ATL-Steuerelement-Assistent](../atl/reference/atl-control-wizard.md) generiert automatisch ein Skript Registrierungsstelle für den COM-Server. Sie finden dieses Skript in der RGS-Datei, die dem-Objekt zugeordnet.  
  
 Die ATL-Registrierung Skriptmodul verarbeitet Ihrer Registrierungsstelle-Skript zur Laufzeit. ATL Ruft das Skriptmodul automatisch beim Server-Setup.  
  
 In diesem Artikel werden die folgenden Themen in Bezug auf die registrierungsskripte behandelt:  
  
-   [Einführung in die BNF-Snytax (Backus Naur Form)](../atl/understanding-backus-nauer-form-bnf-syntax.md)  
  
-   [Einführung in Analysestrukturen](../atl/understanding-parse-trees.md)  
  
-   [Beispiele für die Registrierungsskripterstellung](../atl/registry-scripting-examples.md)  
  
-   [Verwenden von ersetzbaren Parametern (Der Registrierungspräprozessor)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)  
  
-   [Aufruf von Skripts](../atl/invoking-scripts.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Registrierungskomponente (Registrar)](../atl/atl-registry-component-registrar.md)

