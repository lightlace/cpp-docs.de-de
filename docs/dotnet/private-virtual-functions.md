---
title: "Private virtuelle Funktionen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zugriffsmodifizierer [C++], Für Klassenmember"
  - "Abgeleitete Klassen, Virtuelle Funktionen"
  - "Memberzugriff [C++], Virtuelle Member"
  - "Virtuelle Funktionen, Private"
ms.assetid: 04448086-bf72-44be-9c1f-dfda1744949e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Private virtuelle Funktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Private virtuelle Funktionen in abgeleiteten Klassen werden in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] anders behandelt als in Managed Extensions for C\+\+.  
  
 In Managed Extensions schränkt die Zugriffsebene einer virtuellen Funktion nicht die Möglichkeit ein, diese Funktion innerhalb einer abgeleiteten Klasse zu überschreiben.  In der neuen Syntax kann eine virtuelle Funktion keine virtuelle Funktion einer Basisklasse überschreiben, auf die sie keinen Zugriff hat.  Beispiel:  
  
```  
__gc class MyBaseClass {  
   // inaccessible to a derived class   
   virtual void g();  
};  
  
__gc class MyDerivedClass : public MyBaseClass {  
public:  
   // okay in Managed Extensions; g() overrides MyBaseClass::g()  
   // error in new syntax; cannot override: MyBaseClass::g() is inaccessible …  
   void g();  
};  
```  
  
 Die neue Syntax enthält keine echte Entsprechung für diese Art von Design.  Auf die Basisklassenmember muss zugegriffen werden können. Sie dürfen also nicht mehr privat sein.  Die geerbten Methoden müssen nicht über denselben Zugriff verfügen.  In diesem Beispiel besteht die Änderung mit den geringsten Auswirkungen darin, den MyBaseClass\-Member auf `protected` festzulegen.  Dadurch bleibt dem allgemeinen Programm weiterhin der Zugriff auf die Methode über MyBaseClass verwehrt.  
  
```  
ref class MyBaseClass {  
protected:  
   virtual void g();  
};  
  
ref class MyDerivedClass : MyBaseClass {  
public:  
   virtual void g() override;  
};  
```  
  
 Beachten Sie, dass das Weglassen des expliziten `virtual`\-Schlüsselworts in der Basisklasse in der neuen Syntax zu einer Warnmeldung führt.  
  
## Siehe auch  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Membersichtbarkeit](../misc/member-visibility.md)