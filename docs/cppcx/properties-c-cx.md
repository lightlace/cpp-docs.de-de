---
title: Eigenschaften (C + c++ / CX) | Microsoft Docs
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64c7bc56-3191-4cd5-bdf4-476d07d285d5
caps.latest.revision: "12"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 18fb141ab1000d8befda2370f993a5d5ee06d973
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="properties-ccx"></a>Eigenschaften (C++/CX)
Windows-Runtime-Typen, die öffentliche Daten als Eigenschaften verfügbar machen. Clientcode greift auf die Eigenschaft wie auf einen öffentlichen Datenmember zu. Intern wird die Eigenschaft als Block implementiert, der eine "get"-Accessor-Methode, eine "set"-Accessor-Methode oder beide enthält. Durch Verwendung der Accessormethoden können Sie zusätzliche Aktionen ausführen, bevor oder nachdem Sie den Wert abrufen. Beispielsweise können Sie ein Ereignis auslösen oder Validierungsüberprüfungen durchführen.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert einer Eigenschaft ist in einer privaten Variable – dem *Sicherungsspeicher*– enthalten, der vom selben Typ wie die Eigenschaft ist. Eine Eigenschaft kann sowohl einen "set"-Accessor, der dem Sicherungsspeicher einen Wert zuweist, als auch einen "get"-Accessor enthalten, der den Wert des Sicherungsspeichers abruft. Die Eigenschaft ist schreibgeschützt, wenn sie nur einen "get"-Accessor aufweist. Sie ist lesegeschützt, wenn sie nur einen "set"-Accessor aufweist. Wenn beide Accessoren vorhanden sind, ist Lese-/Schreibzugriff (änderbar) möglich.  
  
 Eine *triviale* Eigenschaft ist eine Eigenschaft mit Lese-/Schreibzugriff, für die der Compiler automatisch die Accessoren und den Sicherungsspeicher implementiert. Sie haben keinen Zugriff auf die Implementierung des Compilers. Sie können jedoch eine benutzerdefinierte Eigenschaft deklarieren und deren Accessoren und Sicherungsspeicher explizit deklarieren. Innerhalb eines Accessors können Sie jede benötigte Logik ausführen, z. B. das Überprüfen der Eingabe für den "set"-Accessor, das Berechnen eines Werts vom Eigenschaftswert, den Zugriff auf eine Datenbank oder das Auslösen eines Ereignisses, wenn sich die Eigenschaft ändert.  
  
 Beim Instanziieren einer C++/CX-Verweisklasse wird ihr Speicher mit 0 (Null) initialisiert, bevor der Konstruktor aufgerufen wird. Daher wird allen Eigenschaften zum Zeitpunkt der Deklaration der Standardwert 0 oder "nullptr" zugewiesen.  
  
### <a name="examples"></a>Beispiele  
 Das folgende Codebeispiel zeigt, wie Sie eine Eigenschaft deklarieren und auf sie zugreifen. Die erste Eigenschaft, `Name`, ist als *triviale* Eigenschaft bekannt, da der Compiler automatisch einen `set` -Accessor, einen `get` -Accessor und einen Sicherungsspeicher generiert.  
  
 Die zweite Eigenschaft, `Doctor`, ist eine schreibgeschützte Eigenschaft, da sie einen *Property-Block* angibt, der explizit nur einen `get` -Accessor deklariert. Da der Property-Block deklariert wird, müssen Sie einen Sicherungsspeicher explizit deklarieren, das heißt, die private Zeichenfolgen^-Variable `doctor_`. In der Regel gibt eine schreibgeschützte Eigenschaft nur den Wert des Sicherungsspeichers zurück. Nur die Klasse selbst kann den Wert des Sicherungsspeichers festlegen. Dies geschieht normalerweise im Konstruktor.  
  
 Die dritte Eigenschaft, `Quantity`, ist eine Schreib/-Leseeigenschaft, da sie einen Property-Block deklariert, der sowohl einen `set` -Accessor als auch einen `get` -Accessor deklariert.  
  
 Der `set` -Accessor führt eine benutzerdefinierte Gültigkeitsüberprüfung für den zugeordneten Wert aus. Anders als bei C# ist hier der Name *value* nur der Bezeichner für den Parameter im `set` -Accessor. Er ist kein Schlüsselwort. Wenn *value* nicht größer als null ist, wird Platform::InvalidArgumentException ausgelöst. Andernfalls wird der Sicherungsspeicher `quantity_`mit dem zugeordneten Wert aktualisiert.  
  
 Beachten Sie, dass eine Eigenschaft nicht in einer Memberliste initialisiert werden kann. Sie können Sicherungsspeichervariablen natürlich in einer Memberliste initialisieren.  
  
 [!code-cpp[cx_properties#01](../cppcx/codesnippet/CPP/cx_properties/class1.h#01)]  
  
## <a name="see-also"></a>Siehe auch  
 [Typsystem](../cppcx/type-system-c-cx.md)   
 [Visual C++-Sprachreferenz](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)