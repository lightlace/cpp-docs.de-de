---
title: "Schlüsselwörter (C + c++ / CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: keywords [C++]
ms.assetid: 021013b2-70ac-4df9-aa77-4af1c67a1a67
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e1107ad45feaae470ed2a7481f80bb17c389042d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="language-keywords-ccli"></a>Sprachschlüsselwörter (C++/CLI)
Mehrere Schlüsselwörter, die von Managed Extensions for C++ auf Visual C++ geändert.  
  
 In der neuen Visual C++-Syntax wurde der doppelte Unterstrich entfernt, der alle Schlüsselwörter (mit einer Ausnahme: `__identifier` beibehalten wird). Z. B. eine Eigenschaft ist jetzt als deklariert `property`, nicht `__property`.  
  
 Es wurden zwei Hauptgründe für die Verwendung der doppelte Unterstrich als Präfix in Managed Extensions:  
  
-   Es ist die konforme Methode zum Bereitstellen von lokaler Erweiterungen der ISO C++-Standard. Eine primäre Zweck von Managed Extensions-Entwurf wurde keine Inkompatibilitäten mit der standardmäßigen Sprache, z. B. neue Schlüsselwörter und Token einzuführen. Aus diesem Grund war in großen Bereich, der die Auswahl der Zeigersyntax für die Deklaration von Objekten von verwalteten Verweistypen motiviert.  
  
-   Die Verwendung von der doppelte Unterstrich, abgesehen von der Konformitätsaspekt ist auch nicht invasiv mit vorhandenen Codebasis Benutzer Sprache wird garantiert. Dies war eine zweite Hauptziel des Entwurfs Managed Extensions.  
  
 Trotz entfernen die doppelten unterstrichen, weiterhin Microsoft Standardkonformität. Unterstützung für den dynamischen CLR-Objektmodell ein neues und leistungsfähiges Programmierparadigma darstellt. Unterstützung für dieses neue Paradigma erfordert einen eigenen auf hoher Ebene, Schlüsselwörter und Token. Wir haben gesucht, um einen erstrangige dieses Paradigma-Ausdruck bei der Integration und unterstützen die standardmäßige Sprache bereitstellen. Die neue Syntaxdesign stellt eine erstklassige Programmierung zwei unterschiedliche Objektmodelle bereit.  
  
 Auf ähnliche Weise können wir kümmern, die nicht invasiv Charakter diese neuen Programmiersprachen-Schlüsselworten maximieren. Dies ist mit der Verwendung von kontextbezogenen und durch Leerzeichen getrennten Schlüsselwörtern erreicht wurde. Bevor wir die tatsächlichen neuen Sprachsyntax betrachten, sehen wir versucht, sinnvoll sein, der diese zwei Arten von spezielle Schlüsselwort.  
  
 Ein Kontextabhängiges Schlüsselwort hat eine besondere Bedeutung im Kontext des jeweiligen Programms an. Im allgemeinen Programm, z. B. `sealed` wird als ein normaler Bezeichner behandelt. Allerdings tritt in der einer verwalteten Verweisklassentyp Deklarationsteil, wird es als ein Schlüsselwort im Kontext dieser Klassendeklaration behandelt. Dies minimiert die potenzielle eindringt Auswirkung etwas Einführung in ein neues Schlüsselwort in der Sprache, die wir gerne ist sehr wichtig für Benutzer mit einer vorhandenen Codebasis. Zur gleichen Zeit können sie Benutzern die neue Funktionalität ein erstklassiges Erlebnis des zusätzlichen Sprachfeatures - etwas vorhanden sein, das nicht mit Managed Extentions möglich war. Ein Beispiel dafür, wie `sealed` wird verwendet, finden Sie unter [Deklaration eines verwalteten Klassentyps](../dotnet/declaration-of-a-managed-class-type.md).  
  
 Eine durch Leerzeichen getrennten-Schlüsselwort, z. B. `value class`, ist ein Sonderfall des ein kontextbezogenes Schlüsselwort. Es Paaren existing-Schlüsselwort mit einem Kontextmenü Modifizierer, getrennt durch ein Leerzeichen an. Das Paar wird nicht als zwei getrennte Schlüsselwörter, sondern als einzelne Einheit behandelt.  
  
## <a name="see-also"></a>Siehe auch  
 [C + c++ / CLI Migration Primer](../dotnet/cpp-cli-migration-primer.md)   
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)