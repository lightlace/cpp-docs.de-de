---
title: "Type Forwarding (C++/CLI)"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "type forwarding, Visual C++"
ms.assetid: ae730b69-0c27-41cc-84e1-3132783866ea
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Type Forwarding (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Durch Typweiterleitung können Sie, um einen Typ von einer Assembly \(Assembly A\) zu verschieben in einer anderen Assembly \(Assembly B\), so, dass, es nicht notwendig ist, Clients neu zu kompilieren, die Assembly A nutzen.  
  
## Alle Plattformen  
 Diese Funktion wird nicht in allen Laufzeiten unterstützt.  
  
## Windows\-Runtime  
 Diese Funktion wird in [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] nicht unterstützt.  
  
### Voraussetzungen  
 Compileroption: **\/ZW**  
  
## Common Language Runtime  
 Im folgenden Codebeispiel wird veranschaulicht, wie Typweiterleitung verwendet.  
  
### Syntax  
  
```  
#using "new.dll"  
[assembly:TypeForwardedTo(type::typeid)];  
```  
  
### Parameter  
 `new`  
 Die Assembly, in die Sie die Typdefinition verschieben.  
  
 `type`  
 In dessen Definition des Typs, die Sie in eine andere Assembly verschieben.  
  
### Hinweise  
 Nachdem wird im einer Komponente \(Assembly\) und Clientanwendungen, Sie können keine Typweiterleitung verwenden, um einen Typ aus der Komponente \(Assembly\) in eine andere Assembly verschieben, werden die aktualisierten Bestandteil \(und zusätzliche Assemblys erforderlich\) verwendet, und die Salts funktionieren immer noch, ohne neu kompiliert.  
  
 Typ, der nur Arbeiten für die Komponenten auf die vorhandene Anwendungen weiterleitet.  Wenn Sie eine Anwendung neu erstellen, müssen die entsprechenden Assemblyverweise für Typen geben, die in der Anwendung verwendet werden.  
  
 Wenn ein Typ weitergeleitet wird \(A Typ\) einer Assembly, müssen Sie das `TypeForwardedTo`\-Attribut für diesen Typ sowie einen Verweis hinzufügen.  Die Assembly, die Sie verweisen, muss Folgendes enthalten:  
  
-   Die Definition für Typ. A.  
  
-   Ein `TypeForwardedTo`\-Attribut für Typ A sowie ein Assemblyverweis.  
  
 Beispiele von Typen, die weitergeleitetes enthalten sein können:  
  
-   Verweisklassen  
  
-   Wertklassen  
  
-   Enumerationen  
  
-   interfaces  
  
 Sie können die folgenden Typen weiterleiten:  
  
-   Generische Typen  
  
-   Systemeigene Typen  
  
-   Geschachtelte Typen \(Wenn Sie einen geschachtelten Typ übergeben möchten, sollten Sie den einschließenden Typ übergeben\)  
  
 Sie können einen Typ an einer Assembly weitergeleitet, die in jeder Sprache auf die Common Language Runtime sondern erstellt wird.  
  
 Wenn eine Quellcodedatei, die verwendet wird, um Assembly A.dll erstellen, eine Typdefinition \(`ref class MyClass`\) enthält, und Sie wollte diese Typdefinition in Assembly, B.dll Sie verschieben wurde:  
  
1.  Verschieben Sie die `MyClass`\-Typdefinition in eine Quellcodedatei, die verwendet wird, um B.dll zu erstellen.  
  
2.  Erstellen Sie B.dll Assembly  
  
3.  Löschen Sie die Typdefinition `MyClass` aus Quellcode, der verwendet wird, um A.dll zu erstellen, und ersetzen Sie sie durch Folgendes:  
  
    ```  
    #using "B.dll"  
    [assembly:TypeForwardedTo(MyClass::typeid)];  
    ```  
  
4.  Erstellen Sie Assembly A.dll.  
  
5.  Verwenden Sie A.dll Clientanwendungen, ohne neu zu kompilieren.  
  
### Voraussetzungen  
 Compileroption: **\/clr**