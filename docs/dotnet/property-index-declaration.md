---
title: Eigenschaftenindizes | Microsoft Docs
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
ms.openlocfilehash: 76473ce04cdf5860476b7612ddcbf00b40a0fae1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33160835"
---
# <a name="property-index-declaration"></a>Deklaration von Eigenschaftenindizes
Die Syntax zum Deklarieren einer indizierten Eigenschaft wurde von Managed Extensions für C++ in Visual C++ geändert.  
  
 Die zwei primären Mangel, der die Managed Extensions-sprachunterstützung indizierter Eigenschaften ist die Unfähigkeit in Bezug auf Klassenebene Indizierung bereitstellen. d. h. alle indizierte Eigenschaften sind erforderlich, um ein Name zugewiesen werden und daher besteht keine Möglichkeit, z. B. um einen verwalteten Indexoperator bereitzustellen, die direkt zugewiesen werden kann ein `Vector` oder `Matrix` Klassenobjekt. Ein zweites weniger wichtige Mangel ist, es visuell schwierig ist, eine Eigenschaft, die von einer indizierten Eigenschaft unterscheiden zu können – die Anzahl von Parametern das einzige Anzeichen ist. Schließlich indizierte Eigenschaften beeinträchtigt werden, über die gleichen Probleme wie bei nicht indizierten Eigenschaften - Accessor nicht als eine unteilbare Einheit behandelt, sondern in einzelne Methoden unterteilt.  Zum Beispiel:  
  
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
  
 Wie Sie hier sehen können, unterscheiden sich die Indexer nur durch die zusätzlichen Parameter, geben Sie ein aus zwei oder einzelne Dimension Index. Der Indexer unterscheiden sich in der neuen Syntax wird die schließende Klammer ([,]) hinter den Namen des Indexers und, der angibt, die Anzahl und Typ der einzelnen Indizes:  
  
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
  
 Um einen Indexer auf Klassenebene anzugeben, die direkt auf Objekte der Klasse in der neuen Syntax angewendet werden, können die `default` Schlüsselwort wird wiederverwendet, um einen expliziten Namen zu ersetzen. Zum Beispiel:  
  
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
  
 Beachten Sie, dass es keine einfachen Index-Syntax analog zu den einfachen Eigenschaftensyntax gibt.  
  
## <a name="see-also"></a>Siehe auch  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 