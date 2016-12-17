---
title: "Compilerwarnung (Stufe 1) C4462"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4462"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4462"
ms.assetid: 4e20aca4-293e-4c75-a83d-961c27ab7840
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4462
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermitteln der GUID des Typs nicht möglich.Das Programm kann zur Laufzeit fehlschlagen.  
  
 Warnung C4462 tritt in einer Windows Runtime\-App oder \- Komponente auf, wenn ein öffentlicher `TypedEventHandler` als Typparameter einen Verweis auf die übergeordnete Klasse besitzt.  
  
 **Die Warnung wird durch folgende Art von Code ausgelöst:**  
  
```  
namespace N  
{  
       public ref struct EventArgs sealed {};  
       public ref struct R sealed  
       {  
              R() {}  
              event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;  
       };  
}  
  
[Platform::MTAThread]  
int main()  
{  
     auto x = ref new N::R();  
}  
  
```  
  
 **So beheben Sie den Fehler:**  
  
 Es gibt zwei Möglichkeiten, den Fehler zu umgehen.  Eine Möglichkeit besteht, wie im folgenden Beispiel dargestellt, darin, dem Ereignis internen Zugriff zu gewähren und es somit für den Code in derselben ausführbaren Datei verfügbar zu machen, jedoch nicht für den Code in anderen Windows Runtime\-Komponenten.  
  
```  
  
internal:  
event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;  
  
```  
  
 Wenn das Ereignis öffentlich sein muss, können Sie es mithilfe der anderen Problemumgehung über eine Standardschnittstelle verfügbar machen:  
  
```  
  
ref struct R;  
public interface struct IR { event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e; };  
  
public ref struct R sealed : [Windows::Foundation::Metadata::Default] IR  
{  
    R() {}  
    virtual event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;  
};  
  
```  
  
 Eine GUID vom Typ `Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^` wird nur verwendet, wenn eine andere Komponente auf den Typ zugreift.  Die erste Problemumgehung funktioniert, da auf sie anschließend nur innerhalb der eigenen Komponente zugegriffen werden kann.  Andernfalls muss der Compiler den schlimmsten Fall annehmen und die Warnung ausgeben.