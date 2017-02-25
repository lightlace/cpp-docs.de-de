---
title: "Versiegeln einer virtuellen Funktion | Microsoft Docs"
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
  - "__sealed-Schlüsselwort"
  - "Abgeleitete Klassen, Virtuelle Funktionen"
  - "sealed-Schlüsselwort [C++]"
  - "Virtuelle Funktionen, Versiegeln"
ms.assetid: 0e9fae03-6425-4512-9a24-8ccb6dc8a0d4
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Versiegeln einer virtuellen Funktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Syntax zum Versiegeln einer virtuellen Funktion hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] im Vergleich zu Managed Extensions for C\+\+ geändert.  
  
 Das `__sealed`\-Schlüsselwort wird in Managed Extensions verwendet, um entweder einen Referenztyp zu ändern und dadurch eine nachfolgende Ableitung von diesem nicht zuzulassen \(siehe [Deklaration eines verwalteten Klassentyps](../dotnet/declaration-of-a-managed-class-type.md)\) oder eine virtuelle Funktion zu ändern und dadurch das nachfolgende Überschreiben der Methode in einer abgeleiteten Klasse zu unterbinden.  Beispiel:  
  
```  
__gc class base { public: virtual void f(); };  
__gc class derived : public base {  
public:  
   __sealed void f();  
};  
```  
  
 In diesem Beispiel überschreibt `derived::f()` die `base::f()`\-Instanz auf Grundlage der genauen Übereinstimmung des Funktionsprototyps.  Das `__sealed`\-Schlüsselwort gibt an, dass in einer nachfolgenden, von der abgeleiteten Klasse geerbten Klasse eine Überschreibung von `derived::f()` nicht möglich ist.  
  
 In der neuen Syntax wird `sealed` nach der Signatur eingefügt und darf sich nicht mehr vor dem tatsächlichen Funktionsprototypen befinden, wie dies zuvor möglich war.  Außerdem erfordert die Verwendung von `sealed` auch eine explizite Verwendung des `virtual`\-Schlüsselworts.  Das heißt, die korrekte Übersetzung von `derived` in obigem Beispiel lautet wie folgt:  
  
```  
ref class derived: public base {  
public:  
   virtual void f() override sealed;  
};  
```  
  
 Das Fehlen des `virtual`\-Schlüsselworts in dieser Instanz führt zu einem Fehler.  In der neuen Syntax kann das Kontextschlüsselwort `abstract` anstelle von `=0` verwendet werden, um eine rein virtuelle Funktion anzugeben.  Dies wurde in Managed Extensions nicht unterstützt.  Beispiel:  
  
```  
__gc class base { public: virtual void f()=0; };  
```  
  
 kann umgeschrieben werden als  
  
```  
ref class base { public: virtual void f() abstract; };  
```  
  
## Siehe auch  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [sealed](../windows/sealed-cpp-component-extensions.md)