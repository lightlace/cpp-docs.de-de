---
title: GetProcAddress
ms.date: 11/04/2016
f1_keywords:
- GetProcAddress
helpviewer_keywords:
- DLLs [C++], GetProcAddress
- ordinal exports [C++]
- GetProcAddress method
ms.assetid: 48d14ae0-47ea-4c5d-96b1-2c158f1a26af
ms.openlocfilehash: 7b480314d195f50e4867f646208f2d9c70ce9b14
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220805"
---
# <a name="getprocaddress"></a>GetProcAddress

Prozesse, die explizit Verknüpfen mit einer DLL-Aufrufs [GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress) zum Abrufen der Adresse einer exportierten Funktion in der DLL. Sie rufen die DLL-Funktion dann über den zurückgegebenen Funktionszeiger auf. **GetProcAddress** nimmt als Parameter das DLL-Modulhandle (entweder vom **LoadLibrary**, `AfxLoadLibrary`, oder **GetModuleHandle**), und Sie gelangen Sie entweder den Namen der gewünschten-Funktion zum Aufruf oder die Ordnungszahl für einen Export der Funktion.

Da Sie die DLL-Funktion über einen Zeiger aufrufen und zur Kompilierungszeit keine Typüberprüfung erfolgt, sollten Sie sicherstellen, dass die Parameter für die Funktion korrekt sind, damit Sie nicht den auf dem Stapel belegten Speicherbereich überschreiten und eine Zugriffsverletzung verursachen. Eine Möglichkeit die Typsicherheit zu gewährleisten besteht darin, sich die Funktionsprototypen der exportierten Funktionen anzusehen und entsprechende Typdefinitionen für die Funktionszeiger zu erstellen. Zum Beispiel:

```
typedef UINT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT);
...

HINSTANCE hDLL;               // Handle to DLL
LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer
DWORD dwParam1;
UINT  uParam2, uReturnVal;

hDLL = LoadLibrary("MyDLL");
if (hDLL != NULL)
{
   lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL,
                                           "DLLFunc1");
   if (!lpfnDllFunc1)
   {
      // handle the error
      FreeLibrary(hDLL);
      return SOME_ERROR_CODE;
   }
   else
   {
      // call the function
      uReturnVal = lpfnDllFunc1(dwParam1, uParam2);
   }
}
```

Wie Sie die Funktion sollen angeben, wenn der Aufruf von **GetProcAddress** abhängig, wie die DLL erstellt wurde.

Sie können die Exportordinalzahl nur ermitteln, wenn die DLL, die Sie zum Verknüpfen mit einer Moduldefinitionsdatei (.def) erstellt wurde und die Ordinalzahlen zusammen mit den Funktionen im aufgeführt sind die **EXPORTE** Abschnitt der DEF-Datei der DLL. Aufrufen von **GetProcAddress** Exportordinalzahl und hat den Namen der Funktion, mit einem Export ist etwas schneller, wenn die DLL zahlreiche exportierte Funktionen aufweist, da die Exportordinalzahlen dienen, wie die Tabelle Indizes in der DLLs zu exportieren. Mit einer Exportordinalzahl **GetProcAddress** Exportordinalzahl kann die Funktion direkt und nicht den angegebenen Namen auf den Funktionsnamen in der Exporttabelle der DLL verglichen. Sie sollten jedoch aufrufen **GetProcAddress** mit einer Exportordinalzahl nur dann, wenn Sie die Kontrolle über die Zuordnung der Ordinalzahlen zu den exportierten Funktionen in der DEF-Datei haben.

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](linking-an-executable-to-a-dll.md#linking-implicitly)

- [Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [LoadLibrary und AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)

- [FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary)

- [Exportieren aus einer DLL mithilfe von DEF-Dateien](exporting-from-a-dll-using-def-files.md)

## <a name="see-also"></a>Siehe auch

[Erstellen von C/C++-DLLs in Visual Studio](dlls-in-visual-cpp.md)
