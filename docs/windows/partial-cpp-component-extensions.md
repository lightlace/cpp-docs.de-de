---
title: "Partial (Komponentenerweiterungen f&#252;r C++)"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "partial_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Partiell"
  - "C++/CX, partial"
ms.assetid: 43adf1f5-10c5-44aa-a66f-7507e2bdabf8
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Partial (Komponentenerweiterungen f&#252;r C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit dem Schlüsselwort `partial` können verschiedene Teile der gleichen Verweisklasse unabhängig und in verschiedenen Dateien erstellt werden.  
  
## Alle Laufzeiten  
 \(Diese Sprachfunktion gilt nur für [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].\)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 Bei einer Verweisklasse, die zwei Teildefinitionen besitzt, wird das `partial`\-Schlüsselwort auf die erste Definition angewendet. Dies geschieht normalerweise durch einen automatisch generierten Code, sodass ein menschlicher Programmierer das Schlüsselwort nicht sehr häufig verwendet.  Für alle folgenden Teildefinitionen der Klasse lassen Sie den `partial`\-Modifizierer aus dem *class\-key*\-Schlüsselwort und dem Klassenbezeichner weg.  Wenn der Compiler auf eine bereits definierte Verweisklasse und einen bereits definierten Klassenbezeichner, jedoch nicht auf ein `partial`\-Schlüsselwort trifft, fasst er intern alle Teile der Verweisklassendefinition in einer Definition zusammen.  
  
### Syntax  
  
```cpp  
  
partial class-key identifier {  
   /* The first part of the partial class definition. This is typically auto-generated*/  
}  
// ...  
class-key identifier {  
   /* The subsequent part(s) of the class definition. The same identifier is specified, but the "partial" keyword is omitted. */  
}  
  
```  
  
### Parameter  
 *class\-key*  
 Ein Schlüsselwort, das eine Klasse oder Struktur deklariert, die von [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] unterstützt wird.  Dies ist entweder `ref class`, `value class`, `ref struct` oder `value struct`.  
  
 *identifier*  
 Der Typname des definierten Typs.  
  
### Hinweise  
 Eine partielle Klasse unterstützt Szenarien, in denen Sie einen Teil einer Klassendefinition in einer Datei ändern, und die automatische codegenerierende Software – z. B. der XAML\-Designer – ändert den Code in der gleichen Klasse in einer anderen Datei.  Wenn Sie eine partielle Klasse verwenden, können Sie verhindern, dass der automatische Code\-Generator den Code überschreibt.  In einem Visual Studio\-Projekt wird der Modifizierer `partial` automatisch auf die generierte Datei angewendet.  
  
 Inhalt: Mit zwei Ausnahmen kann eine Definition einer partiellen Klasse alles enthalten, was die vollständige Klassendefinition enthalten kann, wenn das `partial`\-Schlüsselwort weggelassen wurde.  Sie können jedoch Klassenbarrierefreiheit \(beispielsweise `public partial class X {…};`\), oder einen `declspec` angeben.  
  
 Der Zugriffsspezifizierer, die in einer partiellen Klassendefinition für *identifier* verwendet werden, beeinflussen nicht Standardzugriff in einer partiell folgenden oder vollständige Klassendefinition für *identifier*.  Inlinedefinitionen statischer Datenmember sind zulässig.  
  
 Deklaration: Eine Teilausführungsklassendefinition *identifier* stellt nur den Namen *identifier* vorgeschlagen, jedoch *identifier* kann nicht auf eine Weise verwendet werden, die eine Klassendefinition erfordert.  Der Name *identifier* kann nicht verwendet werden, um die Größe zu kennen von *identifier*, oder, Basis oder Member von *identifier* bis nach den Compiler zu verwenden wird die vollständige Definition von *identifier* an.  
  
 Zahl und Reihenfolge: Es kann über null oder mehr geben partielle Klassendefinitionen Klasse für *identifier*.  Jede Definition einer partiellen Klasse von *identifier* muss der eine vollständige Definition von *identifier* lexikalisch vorausgehen \(wenn eine vollständige Definition gibt; Andernfalls kann die Klasse nicht verwendet werden, außer dass FORWARD\-deklariert wurde\) jedoch nicht, müssen Sie Vorwärtsdeklarationen von *identifier* steht.  Alle Klassenschlüssel müssen übereinstimmen.  
  
 Vollständige Definition: Im vollständigen Zeitpunkt der Definition der Klasse *identifier*, ist das Verhalten das Gleiche, als ob die Definition von *identifier* alle Basisklassen, Member, z. B. in der Reihenfolge deklariert hat, in der sie im partiellen Klassen gefunden und definiert wurden.  
  
 Vorlagen: Eine partielle Klasse kann keine Vorlage sein.  
  
 Generika: Eine partielle Klasse kann generisch sein, wenn die vollständige Definition generisch sein kann.  Jede partielle und vollständige Klasse muss jedoch dieselben generischen Parameter und formalen Parameternamen haben.  
  
 Weitere Informationen dazu, wie das `partial`\-Schlüsselwort, finden Sie verwendet [Partielle Klassen \(C\+\+\/CX\)](http://go.microsoft.com/fwlink/p/?LinkId=249023).  
  
### Voraussetzungen  
 Compileroption: **\/ZW**  
  
## Common Language Runtime  
 \(Diese Sprachfunktion gilt nicht für die Common Language Runtime.\)  
  
## Siehe auch  
 [Partielle Klassen \(C\+\+\/CX\)](http://go.microsoft.com/fwlink/p/?LinkId=249023)