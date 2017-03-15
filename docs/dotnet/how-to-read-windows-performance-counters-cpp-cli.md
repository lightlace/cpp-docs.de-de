---
title: "Gewusst wie: Lesen von Windows-Leistungsindikatoren (C++/CLI)"
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
  - "Indikatoren, Lesen von Windows-Leistungsindikatoren"
  - "Leistung"
  - "Leistungsindikatoren"
  - "Leistungsindikatoren, Lesen von Windows-Leistungsindikatoren"
  - "Leistungsüberwachung"
  - "Leistungsüberwachung, Windows-Leistungsindikatoren"
  - "Leistung, Indikatoren"
ms.assetid: 9e1c836c-cb0f-4f37-9a93-3dca6412d6b1
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Lesen von Windows-Leistungsindikatoren (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Einige Anwendungen und Windows\-Subsysteme machen Leistungsdaten durch das Windows\-Leistungssystem verfügbar.  Auf diese Zähler kann mit der <xref:System.Diagnostics.PerformanceCounterCategory>\-Klasse und mit der <xref:System.Diagnostics.PerformanceCounter>\-Klasse zugegriffen werden, die sich im <xref:System.Diagnostics?displayProperty=fullName>\-Namespace befinden.  
  
 Im folgenden Codebeispiel werden diese Klassen verwendet, um einen Zähler abzurufen und anzuzeigen, der von Windows aktualisiert wird, um die prozentuale Prozessorauslastung in Bezug auf die Zeit anzuzeigen.  
  
> [!NOTE]
>  Dieses Beispiel erfordert Administratorrechte für die Ausführung unter Windows Vista.  
  
## Beispiel  
  
```  
// processor_timer.cpp  
// compile with: /clr  
#using <system.dll>  
  
using namespace System;  
using namespace System::Threading;  
using namespace System::Diagnostics;  
using namespace System::Timers;  
  
ref struct TimerObject  
{  
public:  
   static String^ m_instanceName;  
   static PerformanceCounter^ m_theCounter;  
  
public:  
   static void OnTimer(Object^ source, ElapsedEventArgs^ e)  
   {  
      try   
      {  
         Console::WriteLine("CPU time used: {0,6} ",  
          m_theCounter->NextValue( ).ToString("f"));  
      }   
      catch(Exception^ e)  
      {  
         if (dynamic_cast<InvalidOperationException^>(e))  
         {  
            Console::WriteLine("Instance '{0}' does not exist",  
                  m_instanceName);  
            return;  
         }  
         else  
         {  
            Console::WriteLine("Unknown exception... ('q' to quit)");  
            return;  
         }  
      }  
   }  
};  
  
int main()  
{  
   String^ objectName = "Processor";  
   String^ counterName = "% Processor Time";  
   String^ instanceName = "_Total";  
  
   try  
   {  
      if ( !PerformanceCounterCategory::Exists(objectName) )  
      {  
         Console::WriteLine("Object {0} does not exist", objectName);  
         return -1;  
      }  
   }  
   catch (UnauthorizedAccessException ^ex)  
   {  
      Console::WriteLine("You are not authorized to access this information.");  
      Console::Write("If you are using Windows Vista, run the application with ");  
      Console::WriteLine("administrative privileges.");  
      Console::WriteLine(ex->Message);  
      return -1;  
   }  
  
   if ( !PerformanceCounterCategory::CounterExists(  
          counterName, objectName) )  
   {  
      Console::WriteLine("Counter {0} does not exist", counterName);  
      return -1;  
   }  
  
   TimerObject::m_instanceName = instanceName;  
   TimerObject::m_theCounter = gcnew PerformanceCounter(  
          objectName, counterName, instanceName);  
  
   System::Timers::Timer^ aTimer = gcnew System::Timers::Timer();  
   aTimer->Elapsed += gcnew ElapsedEventHandler(&TimerObject::OnTimer);  
   aTimer->Interval = 1000;  
   aTimer->Enabled = true;  
   aTimer->AutoReset = true;  
  
   Console::WriteLine("reporting CPU usage for the next 10 seconds");  
   Thread::Sleep(10000);  
   return 0;  
}  
```  
  
## Siehe auch  
 [Introduction to Monitoring Performance](assetId:///d40f10b9-e2b7-4ec8-a9b3-706929e5bf35)   
 [Windows\-Vorgänge](../dotnet/windows-operations-cpp-cli.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)