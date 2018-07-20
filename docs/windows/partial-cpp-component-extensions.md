---
title: Partial (Komponentenerweiterungen für C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- partial_CPP
dev_langs:
- C++
helpviewer_keywords:
- partial
- C++/CX, partial
ms.assetid: 43adf1f5-10c5-44aa-a66f-7507e2bdabf8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 71c0fc9739e7ef8e1e68c5678ce56fcec4a250c1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880178"
---
# <a name="partial--c-component-extensions"></a>Partial (Komponentenerweiterungen für C++)
Die `partial` Schlüsselwort können Sie verschiedene Teile des gleichen Verweisklasse unabhängig voneinander und in anderen Dateien erstellt werden.  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
 (Diese Sprachfunktion gilt nur für Windows-Runtime).  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 Für eine Verweisklasse, die beiden partielle Definitionen, verfügt die `partial` -Schlüsselwort auf das erste Vorkommen der Definition angewendet wird, und dies erfolgt normalerweise durch automatisch generierte Code, damit eine interaktive Workflowdienste Codierer nicht für das Schlüsselwort sehr häufig verwendet werden. Lassen Sie alle nachfolgenden partiellen Definitionen der Klasse, die `partial` Modifizierer aus der *Klassenschlüssel* Schlüsselwort und die Klasse Bezeichner. Wenn der Compiler erkennt, eine zuvor definierte Verweisklasse und Klassenbezeichner jedoch keine `partial` -Schlüsselwort, intern kombiniert alle Teile der Definition der Ref-Klasse in eine Definition.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
partial class-key identifier {  
   /* The first part of the partial class definition. 
      This is typically auto-generated */  
}  
// ...  
class-key identifier {  
   /* The subsequent part(s) of the class definition. The same 
      identifier is specified, but the "partial" keyword is omitted. */  
}  
```  
  
### <a name="parameters"></a>Parameter  
 *Klassenschlüssel*  
 Ein Schlüsselwort, das deklariert eine Klasse oder Struktur, die von der Windows-Runtime unterstützt wird. Entweder `ref class`, `value class`, `ref struct`, oder `value struct`.  
  
 *identifier*  
 Der Name des definierten Typs.  
  
### <a name="remarks"></a>Hinweise  
 Eine partielle Klasse unterstützt Szenarien, in dem Sie einen Teil der Definition einer Klasse in eine Datei und das automatische Generieren von Code Software ändern – z. B. die Verwendung von XAML-Designer – ändert der Code in der gleichen Klasse in einer anderen Datei. Mithilfe einer partiellen Klasse können Sie verhindern, dass die automatische Codegenerator Ihren Code überschreibt. In einem Visual Studio-Projekt wird der Modifizierer `partial` automatisch auf die generierte Datei angewendet.  
  
 Inhalt: Mit zwei Ausnahmen eine partielle Klassendefinition kann alles enthalten, die die vollständige Klassendefinition enthalten kann, wenn die `partial` -Schlüsselwort ausgelassen wurde. Sie können keine jedoch klassenbarrierefreiheit angeben (z. B. `public partial class X { ... };`), oder ein `declspec`.  
  
 Zugriff auf Spezifizierer verwendet, die in einer partiellen Klassendefinition für *Bezeichner* wirken sich nicht auf die Standard-Barrierefreiheit in einer nachfolgenden partiellen oder vollständigen Klassendefinition für *Bezeichner*. Inlinedefinitionen statischer Datenmember sind zulässig.  
  
 Deklaration: Eine partielle Definition einer Klasse *Bezeichner* führt nur den Namen *Bezeichner*, aber *Bezeichner* kann nicht in einer Weise, die eine Klasse erfordert verwendet werden Definition. Der Name *Bezeichner* kann nicht verwendet werden, um die Größe des wissen *Bezeichner*, oder verwenden eine Basis oder ein Mitglied *Bezeichner* erst nach der Compiler die vollständige Definition der trifft *Bezeichner*.  
  
 Anzahl und Reihenfolge: Es kann NULL oder mehr partielle Klassendefinitionen für *Bezeichner*. Jede partielle Klassendefinition *Bezeichner* muss lexikalisch der einen vollständigen Definition der vorausgehen *Bezeichner* (wenn es eine vollständigen Definition; andernfalls die Klasse kann nicht verwendet werden außer wie Vorwärts deklarierte) jedoch Vorwärtsdeklarationen der müssen nicht vorausgehen *Bezeichner*. Alle Klassenschlüssel müssen übereinstimmen.  
  
 Vollständige Definition: zum Zeitpunkt der vollständigen Definition der Klasse *Bezeichner*, das Verhalten entspricht dem Verhalten wie die Definition der *Bezeichner* deklarierte Cursortyp alle Basisklassen, Member usw. in der Reihenfolge, in der Sie wurden gefunden und in der partiellen Klasse definiert.  
  
 Vorlagen: Eine partielle Klasse kann nicht auf eine Vorlage sein.  
  
 Generika: Eine partielle Klasse kann generisch sein, wenn die vollständige Definition generisch sein kann. Jede Klasse teilweisen oder vollständigen muss jedoch genau die gleichen generischen Parametern, einschließlich formale Parameternamen.  
  
 Weitere Informationen zur Verwendung der `partial` -Schlüsselwort verwenden, finden Sie unter [partielle Klassen (C + c++ / CX)](http://go.microsoft.com/fwlink/p/?LinkId=249023).  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime  
 (Diese Sprachfunktion gilt nicht für die Common Language Runtime.)  
  
## <a name="see-also"></a>Siehe auch  
 [Partielle Klassen (C + c++ / CX)](http://go.microsoft.com/fwlink/p/?LinkId=249023)