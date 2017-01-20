---
title: "Gewusst wie: Schreiben von Daten in die Windows-Registrierung (C++/CLI)"
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
  - "Registrierung, Schreiben in"
  - "Visual C++, Schreiben in Windows-Registrierung"
ms.assetid: 3d40b978-4baa-4779-bfe3-47e2917b757f
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Schreiben von Daten in die Windows-Registrierung (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Code wird mit dem <xref:Microsoft.Win32.Registry.CurrentUser>\-Schlüssel eine nicht schreibgeschützte Instanz der <xref:Microsoft.Win32.RegistryKey>\-Klasse erstellt, die dem **Software**\-Schlüssel entspricht.  Anschließend wird die <xref:Microsoft.Win32.RegistryKey.CreateSubKey*>\-Methode verwendet, um einen neuen Schlüssel zu erstellen und Schlüssel\/Wert\-Paare hinzuzufügen.  
  
## Beispiel  
  
### Code  
  
```  
// registry_write.cpp  
// compile with: /clr  
using namespace System;  
using namespace Microsoft::Win32;  
  
int main()  
{  
   // The second OpenSubKey argument indicates that  
   // the subkey should be writable.   
   RegistryKey^ rk;  
   rk  = Registry::CurrentUser->OpenSubKey("Software", true);  
   if (!rk)  
   {  
      Console::WriteLine("Failed to open CurrentUser/Software key");  
      return -1;  
   }  
  
   RegistryKey^ nk = rk->CreateSubKey("NewRegKey");  
   if (!nk)  
   {  
      Console::WriteLine("Failed to create 'NewRegKey'");  
      return -1;  
   }  
  
   String^ newValue = "NewValue";  
   try  
   {  
      nk->SetValue("NewKey", newValue);  
      nk->SetValue("NewKey2", 44);  
   }  
   catch (Exception^)  
   {  
      Console::WriteLine("Failed to set new values in 'NewRegKey'");  
      return -1;  
   }  
  
   Console::WriteLine("New key created.");  
   Console::Write("Use REGEDIT.EXE to verify ");  
   Console::WriteLine("'CURRENTUSER/Software/NewRegKey'\n");  
   return 0;  
}  
```  
  
## Hinweise  
 .NET Framework kann verwendet werden, um mit der <xref:Microsoft.Win32.Registry>\-Klasse und der [RegistryKey](https://msdn.microsoft.com/en-us/library/microsoft.win32.registrykey.aspx)\-Klasse auf die Registrierung zuzugreifen. Beide Klassen werden im <xref:Microsoft.Win32>\-Namespace definiert.  Die **Registry**\-Klasse ist ein Container für statische Instanzen der <xref:Microsoft.Win32.RegistryKey>\-Klasse.  Jede Instanz stellt einen Stammregistrierungsknoten dar.  Die Instanzen sind <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine> und <xref:Microsoft.Win32.Registry.Users>.  
  
## Siehe auch  
 [Gewusst wie: Lesen von Daten aus der Windows\-Registrierung](../dotnet/how-to-read-data-from-the-windows-registry-cpp-cli.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)