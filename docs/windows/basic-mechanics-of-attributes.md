---
title: Grundlegende Funktionsweise der Attribute | Microsoft-Dokumentation
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
ms.openlocfilehash: 3bb7ff68f9c17f7b90261c2c96630911454842a5
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462491"
---
# <a name="basic-mechanics-of-attributes"></a>Grundlegende Funktionsweise der Attribute
Es gibt drei Möglichkeiten zum Einfügen von Attributen in Ihr Projekt. Erstens können Sie sie manuell in Ihren Quellcode einfügen. Zweitens können Sie sie mit dem Eigenschaftenraster eines Objekts in Ihrem Projekt einfügen. Schließlich können Sie mithilfe der verschiedenen Assistenten einfügen. Weitere Informationen zur Verwendung der **Eigenschaften** Fenster und die verschiedenen Assistenten, finden Sie unter [erstellen und Verwalten von Visual C++-Projekte](../ide/creating-and-managing-visual-cpp-projects.md).  
  
 Als wenn das Projekt erstellt wird, analysiert, der Compiler jede C++-Quelldatei, erzeugt eine Objektdatei. Allerdings ist es, wenn der Compiler ein Attribut trifft, analysiert und syntaktisch überprüft. Der Compiler ruft dann dynamisch ein Attributanbieters zum Einfügen von Code oder andere Änderungen vornehmen, zum Zeitpunkt der Kompilierung. Die-Implementierung des Anbieters, hängt von den Typ des Attributs ab. ATL-bezogene Attribute werden beispielsweise durch Atlprov.dll implementiert.  
  
 Die folgende Abbildung veranschaulicht die Beziehung zwischen dem Compiler und Attributanbieter.  
  
 ![Komponentenattributkommunikation](../windows/media/vccompattrcomm.gif "VcCompAttrComm")  
  
> [!NOTE]
>  Verwendung von Attributen wird den Inhalt der Quelldatei nicht geändert werden. Nur dann, die der generierten Attributcode sichtbar ist, ist während des Debuggens von Sitzungen. Darüber hinaus können für jede Quelldatei im Projekt, eine Textdatei generiert werden, in dem die Ergebnisse der Ersetzung Attribut angezeigt. Weitere Informationen zu dieser Vorgehensweise finden Sie unter [/FX (eingefügten Code zusammenführen)](../build/reference/fx-merge-injected-code.md) und [Debuggen von Injiziertem Code](/visualstudio/debugger/how-to-debug-injected-code).  
  
 -Attribute haben eine Reihe von Eigenschaften, die ihre ordnungsgemäße Nutzung definiert, wie die meisten C++-Konstrukte. Dies wird als den Kontext des Attributs bezeichnet und ist in der Tabelle der Attribut-Kontext für jedes Attribut-Referenzthema behoben wurden. Z. B. die [Co-Klasse](../windows/coclass.md) Attribut kann nur auf einer vorhandenen Klasse oder Struktur angewendet werden, im Gegensatz zu den [Cpp_quote](../windows/cpp-quote.md) -Attribut, das an einer beliebigen Stelle innerhalb einer C++-Quelldatei eingefügt werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../windows/attributed-programming-concepts.md)