---
title: "Linkertoolwarnung LNK4227 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4227"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4227"
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Linkertoolwarnung LNK4227
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Warnung bei Metadatenoperation \(HRESULT\): Warnmeldung  
  
 Der Linker hat bei der Zusammenführung Unterschiede in den Metadaten entdeckt:  
  
-   Eine oder mehrere referenzierte Assemblys bei der derzeit erstellten Assembly.  
  
-   Eine oder mehrere Quellcodedateien in einer Kompilierung.  
  
 LNK4227 kann beispielsweise auftreten, wenn zwei globale Funktionen mit dem gleichen Namen vorhanden sind, bei denen die Parameterinformationen jedoch unterschiedlich deklariert sind \(wenn die Deklarationen nicht bei allen Kompiliereinheiten einheitlich sind\).  Wenn Sie Sie ildasm.exe \/TEXT \/METADATEN `object_file` für jede OBJ\-Datei verwenden, wird deutlich, wie sehr sich die Typen voneinander unterscheiden.  
  
 LNK4227 meldet auch Probleme, die von einem anderen Tool verursacht werden.  Informationen zu **al.exe** finden Sie beispielsweise unter [Fehler und Warnungen des Al.exe\-Tools](assetId:///7f125d49-0a03-47a6-9ba9-d61a679a7d4b).  
  
 Um die Warnung zu vermeiden, müssen die Probleme mit Metadaten behoben werden.  
  
 LNK4227 wird beispielsweise ausgegeben, wenn eine Assembly, auf die verwiesen wird, mit einer anderen Signatur versehen ist als die Assembly, die auf diese Assembly verweist.  
  
 Im folgenden Beispiel wird LNK4227 generiert:  
  
```  
// LNK4227.cpp  
// compile with: /clr  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 und anschließend  
  
```  
// LNK4227b.cpp  
// compile with: /clr LNK4227.cpp /FeLNK4227b.exe  
using namespace System::Reflection;  
using namespace System::Runtime::CompilerServices;  
  
[assembly:AssemblyDelaySignAttribute(true)];  
// Try the following line instead  
// [assembly:AssemblyDelaySignAttribute(false)];  
  
ref class MyClass  
{  
};  
```  
  
 Im folgenden Beispiel wird LNK4227 generiert:  
  
```  
// LNK4227c.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 und anschließend  
  
```  
// LNK4227d.cpp  
// compile with: /clr:oldSyntax LNK4227c.cpp /FeLNK4227d.exe  
#using <mscorlib.dll>  
using namespace System::Reflection;  
using namespace System::Runtime::CompilerServices;  
  
[assembly:AssemblyDelaySignAttribute(true)];  
  
__gc class MyClass  
{  
};  
```  
  
 LNK4227 kann auch generiert werden, wenn Versionsnummern im falschen Format an Assemblyattribute übergeben werden.  Die '\*'\-Notation ist für AssemblyVersionAttribute spezifisch.  Diese Warnung kann vermieden werden, indem für die Versionsattribute nur Zahlen verwendet werden, die sich von AssemblyVersionAttribute unterscheiden.  
  
 Im folgenden Beispiel wird LNK4227 generiert:  
  
```  
// LNK4227e.cpp  
// compile with: /clr /LD /W1  
using namespace System::Reflection;  
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK  
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227  
// try the following line instead  
// [assembly:AssemblyFileVersionAttribute("2.3")];  
```