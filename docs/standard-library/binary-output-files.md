---
title: Binäre Ausgabedateien
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [C++], binary output files
- files [C++], binary output files
- binary data, binary output files
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
ms.openlocfilehash: 4562f5c1167aeadc6689313e73545ed1ad9bbcf8
ms.sourcegitcommit: 878a164fe6d550ca81ab87d8425c8d3cd52fe384
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2019
ms.locfileid: "68376335"
---
# <a name="binary-output-files"></a>Binäre Ausgabedateien

Streams wurden ursprünglich für Text entwickelt, deswegen ist die Standardmethode für die Ausgabe „text“. Im Textmodus wird das Zeilenvorschub Zeichen (Zeilenumbruch) zu einem Wagen Rücklauf-Zeilenvorschub Paar erweitert. Die Erweiterung kann Probleme verursachen, wie hier gezeigt wird:

```cpp
// binary_output_files.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };
int main( )
{
    ofstream os( "test.dat" );
    os.write( (char *) iarray, sizeof( iarray ) );
}
```

Sie erwarten möglicherweise, dass dieses Programm die Bytesequenz { 99, 0, 10, 0 } ausgibt; stattdessen wird { 99, 0, 13, 10, 0 } ausgegeben, wodurch Probleme für ein Programm verursacht werden, das eine binäre Eingabe erwartet. Wenn Sie eine echte binäre Ausgabe benötigen, in der Zeichen nicht übersetzt geschrieben werden, können Sie die binäre Ausgabe mit dem [ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) -Konstruktorargument `openmode` angeben:

```cpp
// binary_output_files2.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };

int main()
{
   ofstream ofs ( "test.dat", ios_base::binary );

   // Exactly 8 bytes written
   ofs.write( (char*)&iarray[0], sizeof(int)*2 );
}
```

## <a name="see-also"></a>Siehe auch

[Ausgabestreams](../standard-library/output-streams.md)
