---
title: Grundlegende Funktionsweise der Attribute | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], inserting in code
- attributes [C++], about attributes
ms.assetid: dc2069c3-b9f3-4a72-965c-4e5208ce8e34
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d6db2994a2606f6c4d0cb4cd581ec46d87ca3d2c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="basic-mechanics-of-attributes"></a>Grundlegende Funktionsweise der Attribute
Es gibt drei Möglichkeiten zum Einfügen von Attributen in Ihrem Projekt ein. Erstens können Sie diese manuell in Ihren Quellcode einfügen. Zweitens können Sie sie mithilfe des Eigenschaftenrasters eines Objekts in Ihrem Projekt einfügen. Schließlich können Sie sie mithilfe der verschiedenen Assistenten einfügen. Weitere Informationen zur Verwendung im Eigenschaftenfenster und den verschiedenen Assistenten finden Sie unter [erstellen und Verwalten von Visual C++-Projekte](../ide/creating-and-managing-visual-cpp-projects.md).  
  
 Als wenn das Projekt erstellt wird, teilt vor, der Compiler jeder C++-Quelldatei, erzeugt eine Objektdatei. Wenn der Compiler ein Attribut gefunden wird, ist es jedoch analysiert und syntaktisch überprüft. Der Compiler ruft dann dynamisch ein Attributanbieters zum Einfügen von Code oder andere Änderungen vornehmen, zum Zeitpunkt der Kompilierung. Die Implementierung des Anbieters unterscheidet sich je nach Typ des Attributs. ATL-bezogene Attribute werden beispielsweise durch Atlprov.dll implementiert.  
  
 Die folgende Abbildung veranschaulicht die Beziehung zwischen dem Compiler und der Attributanbieter.  
  
 ![Komponentenattributkommunikation](../windows/media/vccompattrcomm.gif "VcCompAttrComm")  
  
> [!NOTE]
>  Attributen wird der Inhalt der Quelldatei nicht verändert. Der generierte Attributcode sichtbar ist nur dann ist während des Debuggens von Sitzungen. Darüber hinaus können Sie für jede Quelldatei in das Projekt, eine Textdatei generieren, in dem die Ergebnisse der Attribut-Ersetzung angezeigt. Weitere Informationen zu diesem Verfahren finden Sie unter [/FX (eingefügten Code zusammenführen)](../build/reference/fx-merge-injected-code.md) und [Debuggen von Injiziertem Code](/visualstudio/debugger/how-to-debug-injected-code).  
  
 Attribute aufweisen wie die meisten C++-Konstrukte eine Gruppe von Eigenschaften, die deren ordnungsgemäße Verwendung definiert. Dies wird als dem Kontext des Attributs bezeichnet und ist in den Kontext Attributtabelle für jedes Attribut-Referenzthema adressiert. Z. B. die [Coclass](../windows/coclass.md) Attribut kann nur auf einer vorhandenen Klasse oder Struktur angewendet werden, im Gegensatz zu den [Cpp_quote](../windows/cpp-quote.md) -Attribut, das an einer beliebigen Stelle innerhalb einer C++-Quelldatei eingefügt werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../windows/attributed-programming-concepts.md)