---
title: "Gewusst wie: Abrufen der seit dem Start vergangenen Zeit (C++/CLI)"
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
helpviewer_keywords: 
  - "Indikatoren, Verstrichene Zeit"
  - "Start"
  - "Start, Verstrichene Zeit seit"
  - "Tickzähler"
  - "Uhrzeit, Verstrichen seit dem Start"
ms.assetid: a31fdecc-099e-4dd1-a176-f682289c5dd0
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Abrufen der seit dem Start vergangenen Zeit (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird dargestellt, wie die Tickrate oder die Anzahl der seit dem Start von Windows vergangenen Millisekunden ermittelt werden.  Der Wert wird im <xref:System.Environment.TickCount*?displayProperty=fullName>\-Member gespeichert und ungefähr alle 24,9 Tage auf 0 \(null\) zurückgesetzt, da es sich um einen 32\-Bit\-Wert handelt.  
  
## Beispiel  
  
```  
// startup_time.cpp  
// compile with: /clr  
using namespace System;  
  
int main( )   
{  
   Int32 tc = Environment::TickCount;  
   Int32 seconds = tc / 1000;  
   Int32 minutes = seconds / 60;  
   float hours = static_cast<float>(minutes) / 60;  
   float days = hours / 24;  
  
   Console::WriteLine("Milliseconds since startup: {0}", tc);  
   Console::WriteLine("Seconds since startup: {0}", seconds);  
   Console::WriteLine("Minutes since startup: {0}", minutes);  
   Console::WriteLine("Hours since startup: {0}", hours);  
   Console::WriteLine("Days since startup: {0}", days);  
  
   return 0;  
}  
```  
  
## Siehe auch  
 [Windows\-Vorgänge](../dotnet/windows-operations-cpp-cli.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)