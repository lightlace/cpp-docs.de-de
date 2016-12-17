---
title: "Gewusst wie: Lesen von Daten aus der Windows-Registrierung (C++/CLI)"
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
  - "Registrierung, Lesen"
  - "Visual C++, Lesen aus Windows-Registrierung"
ms.assetid: aebf52c0-acc7-40e2-adbc-d34e0a1e467e
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Lesen von Daten aus der Windows-Registrierung (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird der <xref:Microsoft.Win32.Registry.CurrentUser>\-Schlüssel verwendet, um Daten aus der Windows\-Registrierung zu lesen.  Zunächst werden die Unterschlüssel mit der <xref:Microsoft.Win32.RegistryKey.GetSubKeyNames*>\-Methode aufgelistet, und anschließend wird der Identities\-Unterschlüssel mithilfe der <xref:Microsoft.Win32.RegistryKey.OpenSubKey*>\-Methode geöffnet.  Jeder Unterschlüssel wird wie ein Stammschlüssel durch die <xref:Microsoft.Win32.RegistryKey>\-Klasse dargestellt.  Schließlich werden mit dem neuen <xref:Microsoft.Win32.RegistryKey>\-Objekt die Schlüssel\/Wert\-Paare aufgelistet.  
  
## Beispiel  
  
### Code  
  
```  
// registry_read.cpp  
// compile with: /clr  
using namespace System;  
using namespace Microsoft::Win32;  
  
int main( )  
{  
   array<String^>^ key = Registry::CurrentUser->GetSubKeyNames( );  
  
   Console::WriteLine("Subkeys within CurrentUser root key:");  
   for (int i=0; i<key->Length; i++)  
   {  
      Console::WriteLine("   {0}", key[i]);  
   }  
  
   Console::WriteLine("Opening subkey 'Identities'...");  
   RegistryKey^ rk = nullptr;  
   rk = Registry::CurrentUser->OpenSubKey("Identities");  
   if (rk==nullptr)  
   {  
      Console::WriteLine("Registry key not found - aborting");  
      return -1;  
   }  
  
   Console::WriteLine("Key/value pairs within 'Identities' key:");  
   array<String^>^ name = rk->GetValueNames( );  
   for (int i=0; i<name->Length; i++)  
   {  
      String^ value = rk->GetValue(name[i])->ToString();  
      Console::WriteLine("   {0} = {1}", name[i], value);  
   }  
  
   return 0;  
}  
```  
  
## Hinweise  
 Die <xref:Microsoft.Win32.Registry>\-Klasse ist lediglich ein Container für statische Instanzen von <xref:Microsoft.Win32.RegistryKey>.  Jede Instanz stellt einen Stammregistrierungsknoten dar.  Die Instanzen sind <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine> und <xref:Microsoft.Win32.Registry.Users>.  
  
 Die Objekte innerhalb der <xref:Microsoft.Win32.Registry>\-Klasse sind nicht nur statisch, sondern auch schreibgeschützt.  Darüber hinaus sind Instanzen der <xref:Microsoft.Win32.RegistryKey>\-Klasse, die für den Zugriff auf den Inhalt der Registrierungsobjekte erstellt wurden, ebenfalls schreibgeschützt.  Unter [Gewusst wie: Schreiben von Daten in die Windows\-Registrierung](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md) finden Sie ein Beispiel, in dem dargestellt wird, wie dieses Verhalten überschrieben werden kann.  
  
 In der <xref:Microsoft.Win32.Registry>\-Klasse stehen zwei weitere Objekte zur Verfügung: <xref:Microsoft.Win32.Registry.DynData> und <xref:Microsoft.Win32.Registry.PerformanceData>.  Bei beiden Objekten handelt es sich um Instanzen der <xref:Microsoft.Win32.RegistryKey>\-Klasse.  Das <xref:Microsoft.Win32.Registry.DynData>\-Objekt enthält dynamische Registrierungsinformationen, die nur unter Windows 98 und Windows Me unterstützt werden.  Das <xref:Microsoft.Win32.Registry.PerformanceData>\-Objekt dient dem Zugriff auf Informationen zu Leistungsindikatoren für Anwendungen, die das Leistungsüberwachungssystem von Windows verwenden.  Der <xref:Microsoft.Win32.Registry.PerformanceData>\-Knoten stellt Informationen dar, die eigentlich nicht in der Registrierung gespeichert sind und aus diesem Grund nicht mit Regedit.exe angezeigt werden können.  
  
## Siehe auch  
 [Gewusst wie: Schreiben von Daten in die Windows\-Registrierung](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md)   
 [Windows\-Vorgänge](../dotnet/windows-operations-cpp-cli.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)