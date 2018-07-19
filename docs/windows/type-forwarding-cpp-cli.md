---
title: Typweiterleitung (C + c++ / CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- type forwarding, Visual C++
ms.assetid: ae730b69-0c27-41cc-84e1-3132783866ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9caa2e18a1ec851967857eb068797e092835f587
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891093"
---
# <a name="type-forwarding-ccli"></a>Typweiterleitung (C++/CLI)
*Typweiterleitung* können Sie einen Typ aus einer Assembly (Assembly A) in einer anderen Assembly (Assembly B) verschieben, so, dass es nicht erforderlich ist, Clients neu kompiliert, die Assembly a zu verarbeiten  
  
## <a name="all-platforms"></a>Alle Plattformen  
 Diese Funktion wird in alle Laufzeiten nicht unterstützt.  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 Diese Funktion ist in Windows-Runtime nicht unterstützt.  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime  
 Im folgenden Codebeispiel wird veranschaulicht, wie zum Weiterleiten von Typen zu verwenden.  
  
### <a name="syntax"></a>Syntax  
  
```  
#using "new.dll"  
[assembly:TypeForwardedTo(type::typeid)];  
```  
  
### <a name="parameters"></a>Parameter  
 `new`  
 Die Assembly, in der Sie die Typdefinition verschieben.  
  
 `type`  
 Der Typ, dessen Definition, die Sie in einer anderen Assembly verschieben.  
  
### <a name="remarks"></a>Hinweise  
 Nachdem eine Komponente (Assembly) ausgeliefert wird, und wird von Clientanwendungen verwendet wird, können Sie Typ, Weiterleitung an einen Typ aus der Komponente (Assembly) in einer anderen Assembly zu verschieben, werden die aktualisierten Komponente (und alle zusätzlichen erforderlichen Assemblys) ausgeliefert und dem Client Anwendungen funktionieren weiterhin ohne erneut kompiliert wird.  
  
 Typweiterleitung funktioniert nur für Komponenten, die von einer vorhandenen Anwendung verwiesen wird. Wenn Sie eine Anwendung neu erstellen, müssen die entsprechenden Assemblyverweise für alle Typen, die in der Anwendung verwendet werden.  
  
 Wenn Sie einen Typ (A) aus einer Assembly weitergeleitet werden, müssen Sie Hinzufügen der `TypeForwardedTo` Attribut für diesen Typ als auch einen Assemblyverweis. Die Assembly, die Sie verweisen, muss eine der folgenden enthalten:  
  
-   Die Definition für den Typ a  
  
-   Ein `TypeForwardedTo` Attribut für Geben Sie einen als auch einen Assemblyverweis.  
  
 Beispiele für Typen, die weitergeleitet werden können:  
  
-   Verweisklassen  
  
-   Wertklassen  
  
-   Enumerationen  
  
-   Schnittstellen  
  
 Sie können die folgenden Typen nicht weiterleiten:  
  
-   Generische Typen  
  
-   Systemeigene Typen  
  
-   Geschachtelte Typen (Wenn Sie einen geschachtelten Typ weiterleiten möchten, Sie sollten weiterleiten den einschließenden Typ)  
  
 Sie können einen Typ an einer Assembly in einer beliebigen Sprache für die common Language Runtime erstellt weiterleiten.  
  
 Wenn eine Quellcodedatei, die zum Erstellen der Assembly A.dll eine Typdefinition enthält (`ref class MyClass`), und Sie diesen Typ verschieben möchten Definition auf Assembly B.dll, Sie würden:  
  
1.  Verschieben der `MyClass` Geben Sie die Definition einer Quellcodedatei, die zum Erstellen von B.dll verwendet.  
  
2.  Erstellen Sie die Assembly B.dll  
  
3.  Löschen der `MyClass` Typdefinition im Quellcode verwendet, um A.dll erstellen, und Ersetzen Sie es durch Folgendes:  
  
    ```  
    #using "B.dll"  
    [assembly:TypeForwardedTo(MyClass::typeid)];  
    ```  
  
4.  Erstellen Sie die Assembly A.dll.  
  
5.  Verwenden Sie A.dll ohne erneute Kompilierung Clientanwendungen.  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**