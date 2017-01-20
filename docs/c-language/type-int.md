---
title: "Typ &quot;int&quot;"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "int-Datentyp"
  - "Portabilität [C++], Typ "int""
  - "Ganzzahlen mit Vorzeichen"
  - "Typ "int""
ms.assetid: 0067ce9a-281e-491a-ae63-632952981e13
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Typ &quot;int&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Größe eines `int`\-Elements mit oder ohne Vorzeichen ist die Standardgröße einer ganzen Zahl auf einem bestimmten Computer.  Bei den 16\-Bit\-Betriebssystemen ist der `int`\-Typ z. B. normalerweise 16 Bit oder 2 Bytes.  Bei den 32\-Bit\-Betriebssystemen ist der `int`\-Typ normalerweise 32 Bit oder 4 Bytes.  Daher ist der `int`\-Typ mit dem `short int`\-Typ oder dem **long int**\-Typ äquivalent, und der `unsigned int`\-Typ ist entweder mit dem **unsigned short**\-Typ oder dem `unsigned long`\-Typ äquivalent, abhängig von der Zielumgebung.  Die Typen `int` stehen alle für signierte Werte, es sei denn, sie sind anderweitig bezeichnet.  
  
 Die Typspezifizierer `int` und `unsigned int` \(oder einfach `unsigned`\) definieren bestimmte Funktionen der Programmiersprache C \(z. B. den `enum`\-Typ\).  In diesen Fällen bestimmen die Definitionen von `int` und "unsigned int" für eine bestimmte Implementierung den tatsächlichen Speicher.  
  
 **Microsoft\-spezifisch**  
  
 Ganzzahlen mit Vorzeichen werden in der Zweierkomplementdarstellung ausgedrückt.  Das wichtigste Bit enthält die Zeichen 1 für negative Werte und 0 für positive Werte und Null.  Der Wertebereich ist in [Ganzzahlige Grenzen in C\+\+](../c-language/cpp-integer-limits.md) angegeben, was aus der LIMITS.H\-Headerdatei stammt.  
  
 **END Microsoft\-spezifisch**  
  
> [!NOTE]
>  Die int\-Typspezifizierer sowie die unsignierten int\-Typspezifizierer werden in C\-Programmen viel verwendet, denn sie ermöglichen es dem jeweiligen Computer, Ganzzahlenwerte auf die für den betreffenden Computer effizienteste Art zu bearbeiten.  Da die Größen von int\-Typen und int\-Typen ohne Vorzeichen variieren, sind Programme, die abhängig von einer bestimmten int\-Größe sind, möglicherweise nicht auf andere Computern übertragbar.  Um Programme übertragbarer zu gestalten, können Sie Ausdrücke mit dem sizeof\-Operator \(in [Der Operator sizeof](../c-language/sizeof-operator-c.md) erläutert\) anstelle von hartcodierten Datengrößen verwenden.  
  
## Siehe auch  
 [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md)