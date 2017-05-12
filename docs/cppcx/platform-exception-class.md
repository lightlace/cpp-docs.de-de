---
title: "Platform::Exception-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Exception-Klasse"
ms.assetid: ca1d5a67-3a5a-48fe-8099-f9c38a2d2dce
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Platform::Exception-Klasse
Stellt Fehler dar, die beim Ausführen einer Anwendung auftreten. Benutzerdefinierte Ausnahmeklassen können nicht von `Platform::Exception` abgeleitet werden. Wenn Sie eine benutzerdefinierte Ausnahme benötigen, können Sie `Platform::COMException` verwenden und ein app\-spezifisches HRESULT angeben.  
  
## Syntax  
  
```cpp  
public ref class Exception : Object,    IException,    IPrintable,    IEquatable  
```  
  
## Mitglieder  
 Die `Exception`\-Klasse erbt von der `Object`\-Klasse und den Schnittstellen `IException`, `IPrintable` und `IEquatable`.  
  
 Die `Exception`\-Klasse verfügt auch über die folgenden Arten von Membern.  
  
### Konstruktoren  
  
|Member|Beschreibung|  
|------------|------------------|  
|[Exception::Exception\-Konstruktor](../cppcx/exception-exception-constructor.md)|Initialisiert eine neue Instanz der `Exception`\-Klasse.|  
  
### Methoden  
 Die `Exception`\-Klasse erbt die Methoden `Equals()`, `Finalize()`, `GetHashCode()`, `GetType()`, `MemberwiseClose()` und `ToString()` von [Platform::Object\-Klasse](../cppcx/platform-object-class.md). Die `Exception`\-Klasse verfügt auch über die folgende Methode.  
  
|Member|Beschreibung|  
|------------|------------------|  
|[Exception::CreateException\-Methode](../cppcx/exception-createexception-method.md)|Erstellt eine Ausnahme, die den angegebenen HRESULT\-Wert darstellt.|  
  
### Eigenschaften  
 Die Ausnahmeklasse verfügt auch über die folgenden Eigenschaften:  
  
|Member|Beschreibung|  
|------------|------------------|  
|[Exception::HResult\-Eigenschaft](../cppcx/exception-hresult-property.md)|Das HRESULT, das der Ausnahme entspricht.|  
|[Exception::Message\-Eigenschaft](../cppcx/exception-message-property.md)|Eine Meldung, in der die Ausnahme beschrieben wird. Dieser Wert ist schreibgeschützt und kann nicht geändert werden, nachdem `Exception` erstellt wurde.|  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)