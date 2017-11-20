---
title: "Erstellen von Skripts für ATL-Registrierung | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- scripting, registry scripting
- ATL, registry
- registrar scripts [ATL]
- scripts, Registrar scripts
- scripts, creating
ms.assetid: cbd5024b-8061-4a71-be65-7fee90374a35
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5142d0f5e3ede3a7cdd51af0fc54964b1cecec14
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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

