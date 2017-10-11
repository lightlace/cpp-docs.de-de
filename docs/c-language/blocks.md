---
title: "Blöcke | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- function definitions, blocks in code
- blocks
- compound statements
- statements, compound
ms.assetid: be231a92-c712-464e-ae25-a4becb20f7f5
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 18d04884bacf2cbc03fd68c8ec0489595eb0f4d7
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="blocks"></a>Blöcke
Eine Sequenz von Deklarationen, Definitionen und Anweisungen, die in geschweiften Klammern (**{ }**) eingeschlossen sind, wird als „Block“ bezeichnet. Bei C gibt es zwei Arten von Blöcken. Die „Verbundanweisung“ bestehend aus mindestens einer Anweisung (siehe [Die Verbundanweisung](../c-language/compound-statement-c.md)) ist eine Art von Block. Der andere, die „Funktionsdefinition“, besteht aus einer Verbundanweisung (dem Text der Funktion) und dem zugeordneten „Header“ (dem Funktionsnamen, dem Rückgabetyp und den formalen Parametern). Ein Block in anderen Blöcken wird als "geschachtelt" bezeichnet.  
  
 Beachten Sie, dass, während alle Verbundanweisungen in geschweiften Klammern eingeschlossen sind, nicht alles, was innerhalb der geschweiften Klammern eingeschlossen ist, eine Verbundanweisung bildet. Beispielsweise können die Spezifikationen von Array-, Struktur- oder Enumerationselementen zwar innerhalb der geschweiften Klammern angezeigt werden, sie sind jedoch keine Verbundanweisungen.  
  
## <a name="see-also"></a>Siehe auch  
 [Quelldateien und Quellprogramme](../c-language/source-files-and-source-programs.md)
