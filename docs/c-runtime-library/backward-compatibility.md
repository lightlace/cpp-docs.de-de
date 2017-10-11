---
title: "Abwärtskompatibilität | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- CRT, compatibility
- backward compatibility, C run-time libraries
- compatibility, C run-time libraries
- backward compatibility
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 341dc7f2b16449356fab60f79424f5031ceefd6d
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="backward-compatibility"></a>Abwärtskompatibilität
Um Kompatibilität zwischen Produktversionen bereitzustellen, ordnet die Bibliothek „OLDNAMES.LIB“ alte Namen neuen Namen zu. Beispielsweise wird `open` `_open` zugeordnet. Sie müssen nur dann eine explizite Verknüpfung mit OLDNAMES.LIB herstellen, wenn Sie mit Befehlszeilenoptionen in folgenden Kombinationen kompilieren:  
  
-   `/Zl`(Standardbibliotheknamen von Objektdatei unterdrücken) und `/Ze` (die Standardeinstellung – Microsoft-Erweiterungen verwenden)  
  
-   `/link`(Linker-Steuerelement), `/NOD` („no default library“-Suche) und`/Ze`  
  
 Weitere Informationen zu Compilerbefehlszeilenoptionen finden Sie unter [Compilerreferenz](../build/reference/compiler-options.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Kompatibilität](../c-runtime-library/compatibility.md)
