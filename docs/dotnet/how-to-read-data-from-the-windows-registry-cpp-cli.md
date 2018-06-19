---
title: 'Vorgehensweise: Lesen von Daten aus der Windows-Registrierung (C + c++ / CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, reading from Windows Registry
- registry, reading
ms.assetid: aebf52c0-acc7-40e2-adbc-d34e0a1e467e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 87c882bcf2a7900e1f95ea968407c159333c6cb2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132553"
---
# <a name="how-to-read-data-from-the-windows-registry-ccli"></a>Gewusst wie: Lesen von Daten aus der Windows-Registrierung (C++/CLI)
Im folgenden Codebeispiel wird der <xref:Microsoft.Win32.Registry.CurrentUser>-Schlüssel verwendet, um Daten aus der Windows-Registrierung zu lesen. Zunächst werden die Unterschlüssel mit aufgelistet der <xref:Microsoft.Win32.RegistryKey.GetSubKeyNames%2A> -Methode, und klicken Sie dann der Identities-Unterschlüssel mit geöffnet ist die <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> Methode. Jeder Unterschlüssel wird wie ein Stammschlüssel durch die <xref:Microsoft.Win32.RegistryKey>-Klasse dargestellt. Schließlich werden mit dem neuen <xref:Microsoft.Win32.RegistryKey>-Objekt die Schlüssel/Wert-Paare aufgelistet.  
  
## <a name="example"></a>Beispiel  
  
### <a name="code"></a>Code  
  
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
  
## <a name="remarks"></a>Hinweise  
 Die <xref:Microsoft.Win32.Registry>-Klasse ist lediglich ein Container für statische Instanzen von <xref:Microsoft.Win32.RegistryKey>. Jede Instanz stellt einen Stammregistrierungsknoten dar. Die Instanzen sind <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine> und <xref:Microsoft.Win32.Registry.Users>.  
  
 Die Objekte innerhalb der <xref:Microsoft.Win32.Registry>-Klasse sind nicht nur statisch, sondern auch schreibgeschützt. Darüber hinaus sind Instanzen der <xref:Microsoft.Win32.RegistryKey>-Klasse, die für den Zugriff auf den Inhalt der Registrierungsobjekte erstellt wurden, ebenfalls schreibgeschützt. Ein Beispiel zum Überschreiben dieses Verhaltens finden Sie unter [wie: Schreiben von Daten in der Windows-Registrierung (C + c++ / CLI)](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md).  
  
 In der <xref:Microsoft.Win32.Registry>-Klasse stehen zwei weitere Objekte zur Verfügung: <xref:Microsoft.Win32.Registry.DynData> und <xref:Microsoft.Win32.Registry.PerformanceData>. Bei beiden Objekten handelt es sich um Instanzen der <xref:Microsoft.Win32.RegistryKey>-Klasse. Die <xref:Microsoft.Win32.Registry.DynData> -Objekt enthält dynamische Registrierungsinformationen, die nur unter Windows 98 und WindowsMe unterstützt werden Das <xref:Microsoft.Win32.Registry.PerformanceData>-Objekt dient dem Zugriff auf Informationen zu Leistungsindikatoren für Anwendungen, die das Leistungsüberwachungssystem von Windows verwenden. Die <xref:Microsoft.Win32.Registry.PerformanceData> Knoten enthält Informationen, die eigentlich nicht in der Registrierung gespeichert und daher nicht mit Regedit.exe angezeigt werden können.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Schreiben von Daten in der Windows-Registrierung (C + c++ / CLI)](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md)   
 [Windows-Vorgänge (C + c++ / CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)