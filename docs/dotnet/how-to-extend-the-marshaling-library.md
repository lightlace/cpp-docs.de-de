---
title: "Gewusst wie: Erweitern der Marshallingbibliothek | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Marshaling-Bibliothek, Erweitern"
ms.assetid: 4c4a56d7-1d44-4118-b85f-f9686515e6e9
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# Gewusst wie: Erweitern der Marshallingbibliothek
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird erläutert, wie die Marshallingbibliothek erweitert wird, um mehr Konvertierungen zwischen Datentypen bereitzustellen.  Benutzer können die Marshallingbibliothek für alle Datenkonvertierungen erweitern, die derzeit nicht von der Bibliothek unterstützt werden.  
  
 Sie können die Marshallingbibliothek mit einer von zwei Methoden erweitern \- mit oder ohne [marshal\_context\-Klasse](../dotnet/marshal-context-class.md).  Bestimmen Sie anhand des Themas [Übersicht über das Marshaling in C\+\+](../dotnet/overview-of-marshaling-in-cpp.md), ob eine neue Konvertierung einen Kontext erfordert.  
  
 In beiden Fällen erstellen Sie zuerst eine Datei für neue Marshallingkonvertierungen.  Dies geschieht, um die Integrität der Standarddateien der Marshallingbibliothek zu erhalten.  Wenn Sie ein Projekt auf einen anderen Computer oder für einen anderen Programmierer portieren möchten, müssen Sie die neue Marshallingdatei zusammen mit dem Rest des Projekts kopieren.  Auf diese Weise ist gewährleistet, dass der Empfänger des Projekts die neuen Konvertierungen erhält und keine Bibliotheksdateien ändern muss.  
  
### So erweitern Sie die Marshallingbibliothek mit einer Konvertierung, die keinen Kontext erfordert  
  
1.  Erstellen Sie eine Datei, um die neuen Marshallingfunktionen, z. B. MyMarshal.h, zu speichern.  
  
2.  Nehmen Sie eine oder mehrere der Marschallingbibliotheksdateien auf:  
  
    -   marshal.h für Basistypen.  
  
    -   marshal\_windows.h für Windows\-Datentypen.  
  
    -   marshal\_cppstd.h für STL\-Datentypen.  
  
    -   marshal\_atl.h für ATL\-Datentypen.  
  
3.  Verwenden Sie den Code am Ende dieser Schritte, um die Konvertierungsfunktion zu schreiben.  In diesem Code ist TO der Typ, in den konvertiert wird, FROM der Typ, aus dem konvertiert wird, und `from` der zu konvertierende Parameter.  
  
4.  Ersetzen Sie den Kommentar zu Konvertierungslogik durch Code, um den `from`\-Parameter in ein Objekt des Typs TO zu konvertieren und das konvertierte Objekt zurückzugeben.  
  
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
  
### So erweitern Sie die Marshallingbibliothek mit einer Konvertierung, die einen Kontext erfordert  
  
1.  Erstellen Sie eine Datei, um die neuen Marshallingfunktionen, z. B. MyMarshal.h, zu speichern.  
  
2.  Nehmen Sie eine oder mehrere der Marschallingbibliotheksdateien auf:  
  
    -   marshal.h für Basistypen.  
  
    -   marshal\_windows.h für Windows\-Datentypen.  
  
    -   marshal\_cppstd.h für STL\-Datentypen.  
  
    -   marshal\_atl.h für ATL\-Datentypen.  
  
3.  Verwenden Sie den Code am Ende dieser Schritte, um die Konvertierungsfunktion zu schreiben.  In diesem Code ist TO der Typ, in den konvertiert wird, FROM der Typ, aus dem konvertiert wird, `toObject` ein Zeiger, in dem das Ergebnis gespeichert wird, und `fromObject` der zu konvertierende Parameter.  
  
4.  Ersetzen Sie den Kommentar zur Initialisierung durch Code, um `toPtr` auf den entsprechenden leeren Wert zu initialisieren.  Wenn es z. B. ein Zeiger ist, legen Sie ihn auf `NULL` fest.  
  
5.  Ersetzen Sie den Kommentar zu Konvertierungslogik durch Code, um den `from`\-Parameter in ein Objekt des Typs *TO* zu konvertieren.  Dieses konvertierte Objekt wird in `toPtr` gespeichert.  
  
6.  Ersetzen Sie den Kommentar zum Festlegen von `toObject` durch Code, um `toObject` auf das konvertierte Objekt festzulegen.  
  
7.  Ersetzen Sie den Kommentar zum Bereinigen von systemeigenen Ressourcen durch Code, um von `toPtr` belegten Arbeitsspeicher freizugeben.  Wenn `toPtr` Arbeitsspeicher mit `new` belegt hat, verwenden Sie `delete`, um den Arbeitsspeicher freizugeben.  
  
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
  
## Beispiel  
 Im folgenden Beispiel wird die Marshallingbibliothek mit einer Konvertierung, die keinen Kontext erfordert, erweitert.  In diesem Beispiel werden die Mitarbeiterinformationen durch den Code von einem systemeigenen Datentyp in einen verwalteten Datentyp konvertiert.  
  
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
  
 Im vorherigen Beispiel gibt die `marshal_as`\-Funktion ein Handle an die konvertierten Daten zurück.  Dies geschah, um die Erstellung einer zusätzlichen Kopie der Daten zu verhindern.  Mit der direkten Rückgabe der Variablen wäre eine unnötige Leistungseinbuße verbunden.  
  
  **Verwalteter Name: Jeff Smith**  
**Verwaltete Adresse: 123 Main Street**  
**Verwaltete Postleitzahl: 98111**   
## Beispiel  
 Im folgenden Beispiel werden die Mitarbeiterinformationen durch den Code von einem verwalteten Datentyp in einen systemeigenen Datentyp konvertiert.  Diese Konvertierung erfordert einen Marshallingkontext.  
  
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
  
  **Systemeigener Name: Jeff Smith**  
**Systemeigene Adresse: 123 Main Street**  
**Systemeigene Postleitzahl: 98111**   
## Siehe auch  
 [Übersicht über das Marshaling in C\+\+](../dotnet/overview-of-marshaling-in-cpp.md)