---
title: Eigenschaftenindizes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- indexers
- default indexers
- defaults, indexers
- indexed properties, C++
ms.assetid: d898fdbc-2106-4b6a-8c5c-9f511d80fc2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a6917742b285b3700548b54fef164d01c0594e5e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380464"
---
# <a name="property-index-declaration"></a>Deklaration von Eigenschaftenindizes

Die Syntax zum Deklarieren einer indizierten Eigenschaft wurde für Visual C++ von Managed Extensions for C++ geändert.

Die zwei primären Unzulänglichkeit von der Managed Extensions-sprachunterstützung indizierter Eigenschaften ist die Unfähigkeit, geben Sie auf Klassenebene Indizierung. d. h. alle indizierte Eigenschaften sind erforderlich, um ein Name zugewiesen werden und daher besteht keine Möglichkeit, z. B. um einen verwalteten Indexoperator bereitzustellen, die direkt auf angewendet werden können eine `Vector` oder `Matrix` Klassenobjekt. Ein zweites weniger signifikante Unzulänglichkeit ist, dass es visuell schwierig ist, eine Eigenschaft, die von einer indizierten Eigenschaft unterscheiden zu können – die Anzahl der Parameter der einzige Hinweis darauf ist. Zum Schluss indizierte Eigenschaften weist die gleichen Probleme wie die der nicht indizierten Eigenschaften - Accessoren nicht als eine unteilbare Einheit behandelt, sondern in den einzelnen Methoden unterteilt.  Zum Beispiel:

```
public __gc class Vector;
public __gc class Matrix {
   float mat[,];

public:
   __property void set_Item( int r, int c, float value);
   __property float get_Item( int r, int c );

   __property void set_Row( int r, Vector* value );
   __property Vector* get_Row( int r );
};
```

Wie Sie sehen, unterscheiden sich die Indexer nur durch die zusätzlichen Parameter, geben Sie eine aus zwei oder einzelne Index Dimension. Der Indexer unterscheiden sich in der neuen Syntax wird durch die Klammer ([,]), folgen den Namen des Indexers und, der angibt, die Anzahl und Art der einzelnen Indizes:

```
public ref class Vector {};
public ref class Matrix {
private:
   array<float, 2>^ mat;

public:
   property float Item [int,int] {
      float get( int r, int c );
      void set( int r, int c, float value );
   }

   property Vector^ Row [int] {
      Vector^ get( int r );
      void set( int r, Vector^ value );
   }
};
```

Um einen Indexer auf Klassenebene anzugeben, die direkt auf Objekte der Klasse in der neuen Syntax angewendet werden, können die `default` Schlüsselwort wird erneut verwendet, um einen expliziten Namen ersetzen. Zum Beispiel:

```
public ref class Matrix {
private:
   array<float, 2>^ mat;

public:
   // ok: class level indexer now
   //
   //     Matrix mat;
   //     mat[ 0, 0 ] = 1;
   //
   // invokes the set accessor of the default indexer

   property float default [int,int] {
      float get( int r, int c );
      void set( int r, int c, float value );
   }

   property Vector^ Row [int] {
      Vector^ get( int r );
      void set( int r, Vector^ value );
   }
};
```

Wenn die indizierte Standardeigenschaft in der neuen Syntax-Eigenschaft angegeben wird, werden die beiden folgenden Namen sind reserviert: `get_Item` und `set_Item`. Dies ist, da diese die zugrunde liegenden Namen für die indizierte Standardeigenschaft generiert werden.

Beachten Sie, dass es keine einfachen Index-Syntax ähnlich der Syntax für einfache Eigenschaft gibt.

## <a name="see-also"></a>Siehe auch

[Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)
