---
title: "Serialisierung (C++/CLI)"
ms.custom: na
ms.date: "12/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".NET Framework [C++], Serialisierung"
  - "Verwalteter Code [C++], Serialisieren"
  - "NonSerializedAttribute-Klasse, Verwaltete Anwendungen"
  - "SerializableAttribute-Klasse, Verwaltete Anwendungen"
  - "Serialisierung [C++]"
  - "Serialisierung [C++], Informationen über die Serialisierung"
ms.assetid: 869010ca-74e1-4989-b409-4643cdb94084
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Serialisierung (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Serialisierung \(der Prozess des Speicherns des Status eines Objekts oder Members auf einem permanenten Speichermedium\) von verwalteten Klassen \(einschließlich einzelner Felder und Eigenschaften\) wird durch die <xref:System.SerializableAttribute>\-Klasse und die <xref:System.NonSerializedAttribute>\-Klasse unterstützt.  
  
## Hinweise  
 Wenden Sie das benutzerdefinierte Attribut **SerializableAttribute** auf eine verwaltete Klasse an, um eine ganze Klasse zu serialisieren, oder wenden Sie es nur auf bestimmte Felder oder Eigenschaften an, um Teile einer verwalteten Klasse zu serialisieren.  Verwenden Sie das benutzerdefinierte Attribut **NonSerializedAttribute**, um Felder und Eigenschaften einer verwalteten Klasse von der Serialisierung auszuschließen.  
  
## Beispiel  
  
### **Beschreibung**  
 Im folgenden Beispiel ist die Klasse `MyClass` \(und die Eigenschaft `m_nCount`\) als serialisierbar gekennzeichnet.  Die Eigenschaft `m_nData` ist jedoch nicht serialisiert, wie das benutzerdefinierte Attribut **NonSerialized** angibt:  
  
### Code  
  
```  
// serialization_and_mcpp.cpp  
// compile with: /LD /clr  
using namespace System;  
  
[ Serializable ]  
public ref class MyClass {  
public:  
   int m_nCount;  
private:  
   [ NonSerialized ]  
   int m_nData;  
};  
```  
  
### Kommentare  
 Auf beide Attribute kann unter Verwendung des kurzen Namens \(**Serializable** und **NonSerialized**\) verwiesen werden.  Dies wird unter [Anwenden von Attributen](../Topic/Applying%20Attributes.md) ausführlich erläutert.  
  
## Siehe auch  
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)