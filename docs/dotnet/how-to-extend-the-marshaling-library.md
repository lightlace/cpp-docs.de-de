---
title: 'Vorgehensweise: Erweitern der Marshallingbibliothek | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Marshaling Library, extending
ms.assetid: 4c4a56d7-1d44-4118-b85f-f9686515e6e9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6f6503cbb0006c0c8b2e1ed113a798a23ac2ff55
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33135884"
---
# <a name="how-to-extend-the-marshaling-library"></a>Gewusst wie: Erweitern der Marshallingbibliothek
In diesem Thema erläutert das Erweitern der Marshallingbibliothek, um weitere Umwandlungen zwischen Datentypen bereitzustellen. Benutzer können die Marshallingbibliothek für alle Data-Konvertierungen, die derzeit nicht von der Bibliothek unterstützt erweitern.  
  
 Sie können angeben, Erweitern der Marshallingbibliothek auf zwei Arten - mit oder ohne ein [Marshal_context-Klasse](../dotnet/marshal-context-class.md). Überprüfen Sie die [Overview of Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md) Thema, um zu bestimmen, ob eine neue Konvertierung einen Kontext benötigt.  
  
 In beiden Fällen erstellen Sie zuerst eine Datei für die neue Marshalling Konvertierungen. Dies geschieht, um die Integrität des Standards Marshallingbibliothek beizubehalten. Wenn Sie ein Projekt auf einen anderen Computer oder einem anderen Programmierer portieren möchten, müssen Sie die neue Marshalling-Datei zusammen mit dem Rest des Projekts kopieren. Auf diese Weise wird der Benutzer das Projekt wird sichergestellt werden, um die neue Konvertierungen empfangen und muss keine Bibliotheksdateien ändern.  
  
### <a name="to-extend-the-marshaling-library-with-a-conversion-that-does-not-require-a-context"></a>Zum Erweitern der Marshallingbibliothek mit einer Konvertierung erfordert, die einen Kontext keine  
  
1.  Erstellen Sie eine Datei, um die neuen Marshallen Funktionen, z. B. MyMarshal.h zu speichern.  
  
2.  Eine oder mehrere der Marshallingbibliotheksdateien einschließen:  
  
    -   Marshal.h für Basistypen.  
  
    -   marshal_windows.h für Windows-Datentypen.  
  
    -   marshal_cppstd.h für C++-Standardbibliothek-Datentypen.  
  
    -   marshal_atl.h für ATL-Datentypen.  
  
3.  Verwenden Sie den Code am Ende der folgenden Schritte aus, um die Konvertierungsfunktion zu schreiben. In diesem Code ist der Zieltyp der Konvertierung, FROM ist der Typ, aus dem konvertiert und `from` ist der Parameter konvertiert werden.  
  
4.  Ersetzen Sie den Kommentar zum Konvertierungslogik durch Code zum Konvertieren der `from` Parameter in ein Objekt des zu geben und gibt das konvertierte Objekt.  
  
```  
namespace msclr {  
   namespace interop {  
      template<>  
      inline TO marshal_as<TO, FROM> (const FROM& from) {  
         // Insert conversion logic here, and return a TO parameter.  
      }  
   }  
}  
```  
  
### <a name="to-extend-the-marshaling-library-with-a-conversion-that-requires-a-context"></a>Die Marshallingbibliothek mit einer Konvertierung zu erweitern, die einen Kontext benötigt  
  
1.  Erstellen Sie eine Datei zum Speichern der neuen Marshallen Funktionen, z. B. MyMarshal.h  
  
2.  Eine oder mehrere der Marshallingbibliotheksdateien einschließen:  
  
    -   Marshal.h für Basistypen.  
  
    -   marshal_windows.h für Windows-Datentypen.  
  
    -   marshal_cppstd.h für C++-Standardbibliothek-Datentypen.  
  
    -   marshal_atl.h für ATL-Datentypen.  
  
3.  Verwenden Sie den Code am Ende der folgenden Schritte aus, um die Konvertierungsfunktion zu schreiben. In diesem Code ist der Zieltyp der Konvertierung, FROM ist der Typ, aus dem konvertiert `toObject` ist ein Zeiger, in dem das Ergebnis gespeichert und `fromObject` ist der Parameter konvertiert werden.  
  
4.  Ersetzen Sie den Kommentar zum Initialisieren von mit Code zum Initialisieren der `toPtr` auf den entsprechenden leeren Wert. Z. B. wenn es ein Zeiger ist, legen Sie es auf `NULL`.  
  
5.  Ersetzen Sie den Kommentar zum Konvertierungslogik durch Code zum Konvertieren der `from` Parameter in ein Objekt des *TO* Typ. Dieser konvertierte Objekt im gespeichert `toPtr`.  
  
6.  Ersetzen Sie den Kommentar zu Einstellung `toObject` mit Code aus, um `toObject` auf das konvertierte Objekt.  
  
7.  Ersetzen Sie den Kommentar zum Bereinigen von systemeigenen Ressourcen durch Code, um alle von belegten Arbeitsspeicher freizugeben `toPtr`. Wenn `toPtr` reservierter Speicher mit `new`, verwenden Sie `delete` um den Arbeitsspeicher freizugeben.  
  
```  
namespace msclr {  
   namespace interop {  
      template<>  
      ref class context_node<TO, FROM> : public context_node_base  
      {  
      private:  
         TO toPtr;  
      public:  
         context_node(TO& toObject, FROM fromObject)  
         {  
            // (Step 4) Initialize toPtr to the appropriate empty value.  
            // (Step 5) Insert conversion logic here.  
            // (Step 6) Set toObject to the converted parameter.  
         }  
         ~context_node()  
         {  
            this->!context_node();  
         }  
      protected:  
         !context_node()  
         {  
            // (Step 7) Clean up native resources.  
         }  
      };  
   }  
}   
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erweitert die Marshallingbibliothek mit einer Konvertierung, die keinen Kontext benötigt. In diesem Beispiel konvertiert der Code die Mitarbeiterinformationen aus einem systemeigenen Datentyp in einen verwalteten Datentyp.  
  
```  
// MyMarshalNoContext.cpp  
// compile with: /clr  
#include <msclr/marshal.h>  
  
value struct ManagedEmp {  
   System::String^ name;  
   System::String^ address;  
   int zipCode;  
};  
  
struct NativeEmp {  
   char* name;  
   char* address;  
   int zipCode;  
};  
  
namespace msclr {  
   namespace interop {  
      template<>  
      inline ManagedEmp^ marshal_as<ManagedEmp^, NativeEmp> (const NativeEmp& from) {  
         ManagedEmp^ toValue = gcnew ManagedEmp;  
         toValue->name = marshal_as<System::String^>(from.name);  
         toValue->address = marshal_as<System::String^>(from.address);  
         toValue->zipCode = from.zipCode;  
         return toValue;  
      }  
   }  
}  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {   
   NativeEmp employee;  
  
   employee.name = "Jeff Smith";  
   employee.address = "123 Main Street";  
   employee.zipCode = 98111;  
  
   ManagedEmp^ result = marshal_as<ManagedEmp^>(employee);  
  
   Console::WriteLine("Managed name: {0}", result->name);  
   Console::WriteLine("Managed address: {0}", result->address);  
   Console::WriteLine("Managed zip code: {0}", result->zipCode);  
  
   return 0;  
}  
```  
  
 Im vorherigen Beispiel die `marshal_as` Funktion gibt ein Handle an die konvertierten Daten zurück. Dies erfolgte, um zu verhindern, dass eine zusätzliche Kopie der Daten erstellen. Die Variable direkt zurückgeben würde eine unnötige Leistungseinbuße es zugeordnet haben.  
  
```Output  
Managed name: Jeff Smith  
Managed address: 123 Main Street  
Managed zip code: 98111  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel werden die Mitarbeiterinformationen aus einem verwalteten Datentyp in einen systemeigenen Datentyp konvertiert. Diese Konvertierung erfordert einen Marshallingkontext.  
  
```  
// MyMarshalContext.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr/marshal.h>  
  
value struct ManagedEmp {  
   System::String^ name;  
   System::String^ address;  
   int zipCode;  
};  
  
struct NativeEmp {  
   const char* name;  
   const char* address;  
   int zipCode;  
};  
  
namespace msclr {  
   namespace interop {  
      template<>  
      ref class context_node<NativeEmp*, ManagedEmp^> : public context_node_base  
      {  
      private:  
         NativeEmp* toPtr;  
         marshal_context context;  
      public:  
         context_node(NativeEmp*& toObject, ManagedEmp^ fromObject)  
         {  
            // Conversion logic starts here  
            toPtr = NULL;  
  
            const char* nativeName;  
            const char* nativeAddress;  
  
            // Convert the name from String^ to const char*.  
            System::String^ tempValue = fromObject->name;  
            nativeName = context.marshal_as<const char*>(tempValue);  
  
            // Convert the address from String^ to const char*.  
            tempValue = fromObject->address;  
            nativeAddress = context.marshal_as<const char*>(tempValue);  
  
            toPtr = new NativeEmp();  
            toPtr->name = nativeName;  
            toPtr->address = nativeAddress;  
            toPtr->zipCode = fromObject->zipCode;  
  
            toObject = toPtr;  
         }  
         ~context_node()  
         {  
            this->!context_node();  
         }  
      protected:  
         !context_node()  
         {  
            // When the context is deleted, it will free the memory  
            // allocated for toPtr->name and toPtr->address, so toPtr  
            // is the only memory that needs to be freed.  
            if (toPtr != NULL) {  
               delete toPtr;  
               toPtr = NULL;  
            }  
         }  
      };  
   }  
}   
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   ManagedEmp^ employee = gcnew ManagedEmp();  
  
   employee->name = gcnew String("Jeff Smith");  
   employee->address = gcnew String("123 Main Street");  
   employee->zipCode = 98111;  
  
   marshal_context context;  
   NativeEmp* result = context.marshal_as<NativeEmp*>(employee);  
  
   if (result != NULL) {  
      printf_s("Native name: %s\nNative address: %s\nNative zip code: %d\n",  
         result->name, result->address, result->zipCode);  
   }  
  
   return 0;  
}  
```  
  
```Output  
Native name: Jeff Smith  
Native address: 123 Main Street  
Native zip code: 98111  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über das Marshalling in C++](../dotnet/overview-of-marshaling-in-cpp.md)