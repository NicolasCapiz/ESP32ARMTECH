<template>
  <nav class="bg-gray-800">
  <div class="max-w-7xl mx-auto px-2 sm:px-6 lg:px-8">
    <div class="relative flex items-center justify-between h-16">
      <div class="flex-1 flex items-center justify-center sm:items-stretch sm:justify-start">
        <div class="flex-shrink-0 flex items-center">
          <h1 class="text-gray-300">ESP32 Arm Tech</h1>
        </div>
        <div class="hidden sm:block sm:ml-6">
          <div class="flex space-x-4">
            <!-- Current: "bg-gray-900 text-white", Default: "text-gray-300 hover:bg-gray-700 hover:text-white" -->
            <a href="#" class="bg-gray-900 text-white px-3 py-2 rounded-md text-sm font-medium" aria-current="page">Dashboard</a>

            <a href="#" class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium">Team</a>

            <a href="#" class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium">Projects</a>

            <a href="#" class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium">Calendar</a>
          </div>
        </div>
      </div>
      
      </div>
    </div>

  <!-- Mobile menu, show/hide based on menu state. -->
  <div class="sm:hidden" id="mobile-menu">
    <div class="px-2 pt-2 pb-3 space-y-1">
      <!-- Current: "bg-gray-900 text-white", Default: "text-gray-300 hover:bg-gray-700 hover:text-white" -->
      <a href="#" class="bg-gray-900 text-white block px-3 py-2 rounded-md text-base font-medium" aria-current="page">Dashboard</a>

      <a href="#" class="text-gray-300 hover:bg-gray-700 hover:text-white block px-3 py-2 rounded-md text-base font-medium">Team</a>

      <a href="#" class="text-gray-300 hover:bg-gray-700 hover:text-white block px-3 py-2 rounded-md text-base font-medium">Projects</a>

      <a href="#" class="text-gray-300 hover:bg-gray-700 hover:text-white block px-3 py-2 rounded-md text-base font-medium">Calendar</a>
    </div>
  </div>
  </nav>
  <div class="p-20 w-100 text-lg ">
    <h2 class="text-bold text-left text-4xl">Introduccion</h2>
    <div class="flex">
      <p class="w-2/4">Con un servidor web alojado en un ESP32 podremos controlar los movimientos de un brazo robot, en este caso el brazo seleccionado es <a href="https://cults3d.com/en/3d-model/gadget/diy-arduino-robot-arm-with-smartphone-control" class="bg-gray-400 text-white px-3 py-2 rounded-md text-base font-medium">EEZYbotARM MK2</a>. Este modelo lo podemos descargar desde Thingiverse e imprimirlo con una impresora 3d. El servidor web es basado en un proyecto de <a href="https://www.youtube.com/watch?v=RNpHQ1kUMDU"  class="bg-gray-400 text-white px-3 py-2 rounded-md text-base font-medium">FABRI creato</a>, el cual fue modificado para agregar los servos correspondientes a cada eje.</p>
      <div class="w-2/4">
        <img class="mx-auto" src="https://howtomechatronics.com/wp-content/uploads/2018/09/Arduino-Robotic-Arm-3D-Printed.jpg?ezimgfmt=rs:352x367/rscb2/ng:webp/ngcb2" alt="">
      </div>
      
    </div>
  </div>
  <div>
    <h3>Componentes</h3>
    <div class="bg-white">
  <div class="max-w-2xl mx-auto py-16 px-4 sm:py-24 sm:px-6 lg:max-w-7xl lg:px-8">
    <h2 class="sr-only">Products</h2>

    <div class="grid grid-cols-1 gap-y-10 sm:grid-cols-2 gap-x-6 lg:grid-cols-3 xl:grid-cols-4 xl:gap-x-8">
      <a href="#" class="group">
        <div class="w-full aspect-w-1 aspect-h-1 bg-gray-200 rounded-lg overflow-hidden xl:aspect-w-7 xl:aspect-h-8">
          <img src="https://http2.mlstatic.com/D_NQ_NP_855713-MLA44575185419_012021-O.jpg" alt="Tall slender porcelain bottle with natural clay textured body and cork stopper." class="w-full h-full object-center object-cover group-hover:opacity-75">
        </div>
        <h3 class="mt-4 text-sm text-gray-700">ESP32</h3>
        <p class="mt-1 text-lg font-medium text-gray-900">$48</p>
      </a>

      <a href="#" class="group">
        <div class="w-full aspect-w-1 aspect-h-1 bg-gray-200 rounded-lg overflow-hidden xl:aspect-w-7 xl:aspect-h-8">
          <img src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wCEAAoHCBUWFBgVFRQWGBgaGhwYGBgYGBkYGRgYGRoaGhgYGB0cIS4lHCErHxgWJjgmKy8xNTY2HSQ7QDszQi40NjEBDAwMEA8QHhISHzYrISs0NDQ9NzQ0NDQ2NDc0NDQ0ODo2OjE0NDQ/NzQ/NDU0NDo0NTQ0NDU0NDQ/NTQxNDY0NP/AABEIAOEA4QMBIgACEQEDEQH/xAAcAAEAAQUBAQAAAAAAAAAAAAAABAIDBQYHAQj/xAA/EAACAQIEBAMFBgQEBgMAAAABAgADEQQSITEFBkFRImFxEzKBkaEHQlJiscEUctHwI4KSomPC0uHi8RUzQ//EABkBAQADAQEAAAAAAAAAAAAAAAABAgMEBf/EACsRAQACAgEEAQIEBwAAAAAAAAABAgMRBBIhMUETIlEFYXGRI4GhwdHh8P/aAAwDAQACEQMRAD8A7NERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERARLVWqqqWZgqgXLEgADuSdpzfm3n83NHBsLbNW7+SX2H5vl3gb9j+K0KNva1VQnZSfE38qjU/AS2nF6bXsw03zHL8rzgb49kf2pJZwcxZiSSw8z185s/D+a8Exao3tVdlylARlJ0sR4TlJJPXofKYZr2rrphripFt7b1iedUpVMtekyob5KiHODbcMtgVPpeZjhvMGGxGlGsjH8N7N/paxnFePceWtYICEU+Eb2FyAW8z39JiQ/nY9PhL4Zm1d28q5KxW2ofS0Tjf2bcXrDFpQ9ofZuHzITcFghZSt/dNx03vOm8L5hw+Id0pVAXRirIfC3hNiyg7r5iaKMvERAREQEREBERAREQEREBERAREQEREDyImucb5to0Caa3rVtvZ09bH87bL+vlCYiZ8NgdgASSABqSdABNR4/wA/YegCtI+3fpkPgB/M+3wF/hNaxuMq4tmXE11AXX+Eotaw/wCIdzbr27WkHH8u06ozULU3tbIdUe21vP6/zbC8Y5mNt68a1qzaGE45zNiMU3+K/hvcU18KD4dT5m5mEq1coLHpv6dZJr4V0co6lWH3T+o7iR3QEEd7ysueYmJ1KOMWL+KxNwwv7r2OYW/pHtsG2Ys1Wk17hfZhx6AhhceoExdShVpHTxJ6Zh8RuJcpcRYDZB9B8iplLViy1bTVJ/jQPCgZUPvOwsWtrZQL2F9dyfSUPijmUbMxAC9VW4uzeZ7SJVxTubDKD+RSP1sB8JMwWACkO183S5vr32kxEVjUIm0zO5ZNsUUIcMVIIsQbG500+cqSq6lWpuEYG+ZdG/ytfwf3tMLjqhd1UbKb+pG37/OSvZM+rnToo2+PeWQ659n3PrYmqMJW8dQBstQAqTkFyHBABOh1Hy6zpU4ZwTjuBwlq1HBucXlIao1Q+zLMPG4XNoPIAaaXmS+zXjtWpxB0aoSKivUdful9wQOh1O3SQOwxEQEREBERAREQEREBERAREQESHxDH06CGpVcKq7se/QAbknsJzHmT7SXe6YVTTTb2jWzt/KNk9dT6QL/PPM9dcU2FLmlSAW5Q+Nwyg3LbqLm1hbbrGHwtP2RFBb03ADMhIqAm27DVdeo0OxvtOVY1C9cVHLEt7zFiSWsdWJ1PTWZjhXGKuGcEMSvX/wAh+/zmlZiO0ujDlrXtaO0tyXhlPDo1N6agA5hiLlGVvuByDemRcm4OQ26nwnyhi2C3qKwpkhUrsAoc21zqNV1DWewBABIW8n8J4zTxK6aPa2XTY6G19CD+E6Hp2lkhkZggzobq9HW9jYH2RbWwGb/D03OU/dltTHerWKXx/XincK+IYWnXXLWH8tQauumhJHvC1td/UaTSeL8GfDvdvEh9yoNVIO17bHpf9NpseEqqpUUSxpH/AOzOAiUSVUn2Z6MDmBprmFwdVkbivMtNEamgzgnVntlv+UdPhv36SZmtq7nsvf4stOq3aWquZj8RQQ6nT42lFbHanILC5PkL9B2HlITuWNyfn+wnPMuHpSkqImqj49/nL9Oqd9r9W3+AmM9oBtv3OplDYg9ZG1uj7swlRBc3uepO5lgcQ8RFvjMelQxVqLvufpETJasQ3jl7kvFY4qyWp0MqXqvsTlBYIo1cg37DznYuV+UsPgltSXM5Fmqvq7eQ/CvkPrvMR9j1fNwun+V6i/7yf+abzJ0pMvYiJKCIiAiIgIiICIiAiIgIiWqtRVUszBVAuWJAAHck7QNa+0Xhy1sEwN/A6OCNwb5b/wC6cNxdF6LZX1B91xsfWdP545/pewqUcMvtWKkFzcIttbr1c3HkPMzhmJxtSo+Z3Yt3J0HoNgJIz1XxKw7jS30tMbQ4qQLOpPmP3ElUKVRUzsoy9gw+YHT0luphVfxA2PcfuIHtDjARgyM6m+1tu9tfpN4wvOKPSzOgeoNj0P8AP3t5/UTQf/jidM/0lnCIyMQbgW1HQ9jLRaY8Ncea2PxLZ+K8bq12JdyR2+6Ph1mt4hixJLXA+XxMlrRZ/e0HYfvLlbDrkKiw0lZnflS1rWncyxJqDp/fpLT1Z5XpMu/0lkCV1vynq1HZ6Xj1nhbt85TJ0r1SrNSeKZSFlQWB377Da18BUQ/drt/uRDOkz5z5B5nbC0a6gkAsr6Ak3sQdtthM/h/tGfN7xP8Am1+RtOXJntW0xFJnXt14uJ8leqLRH5TPd22JovA+d1ewY3PY+Fvh3m5YbFLUW6m/6iTi5OPJOvE/aWWbjZMM/VH8/SVE8ns6WBETwmB5PZg8Zx9FvlFwOt7Any7+s1Di3MteuxSmSiA2ZlvmY/hHUny+c555OOJmInevLpx8TLfWo8ulzwzSeDcUq0QBUbMvZ2uwv3Y6D0m34XEB1DLsfpJw8nHl7VlXNx74p7+PukRETfTB7OGfadxfEDEVUqufZq3+FTBspFgVNhudbknb5Tuc13jfKmHxNalWqBr03DlRbK5UeEPcHTQbb2tA4zwnlDiGIphxh3CMPvFKeYHsrENa3WafjsCEqtSW7ZTlvcb9enQ3HwnQ+a8TjlZ0qYisyZiCuZkA1sAyggZbWN9po2KR7EAhRbVup8h2H1/SShisRRCWAbMettgemveXMJiyCAT5A/se4npwD/dAPkN5QcOVysCrdcouSP5tLdO8JZpqhKixA01tqR8xYfWWHrovmf73PWRyxalcevyJkNDAm/xz3j2zHc/0kawG/wApbqMTI0tE6hViawPnIhMv+yPaPZGSqsBZcCS6tKX0pQI605dGHkpaUk00gdA+xF1SriQd2RPkrH/qnTOKcBweJBFehTf81grD0ZbMPnOUfZotsU9utM/RlM61SpnvIlMTpzvjf2dVcPepg3aqg1NFvfUfkI963wPrL/KXMZBAJN9td7jdWHedEGddZovO/BgpONorY/8A7oulx0qDzB3+fecfJ40Xjqr2tHeJejxeVv8AhZe9Z/o6LhcQtRQw/wDR85InP+UuPbAm+mvmOhHnNu4txRaNE1Qj1NsqILsxY2AHYdydheONyfkrMX7THn/Lm5PGtiv0+vTJTW+OcTvmRTZV99vxEbqD27/3fnPGaGKrs+JrVXpnVkpPUUqijUKoQWXS+t79TeQMHxetiAmHLBlIJDbs6j7h721v3tr1lc+b5KTGKY7eZ+0NOPg1ePkjW/DO4vGtVaynKvf8Kfi/mPQdtZcxWJp4Sj7Vxra1NB7217Dux1JPQSTg8KtMgMQWJuBvr1Y/iP6SjjGApO9OpWbw0iWVTYBnNvEx62sLKPrPI+XHOqRP0x9vMz/t6991jpr5n2w3EaD1KNKs9w7MDl6KG1sB+86ry1TIwyX3Iv8AOaPRHt3RbHLe4HW3Qntft6To2DHhAtawAHoJ3fhtbTM2mNRG4/dx/iOX6K0972k2iInrvHexEQMTxrgtPELZhZgPCwGo8j3HlOHc48qtTxC0PdDeNmAJUKL6jyNtB30n0PNA+0Wj46b90K/6Tf8A54HL3xGGS2RHYrouthptfXvvpeanUolXvmtrfw73PlNx4jwxne6WAPva2+JHWMHwVEOdvG/c7D0H7ydG2sAEA5lIvr7oHnc9JCrVACdLTZOPU/H6rMFSwHUwIalmOgmRo4bTXeSaWHA2EvZYEVqA7S01KTyJbKwIi0pdVJetKfSACytFhU76/pJ2A4dVrtlopmP4yDkX+sDZ/s1ot/FZgpyhGDHoL7XnYaYsLmwA1JOgHrNS5H5ZbDJ43Luxux2F+wHQS3zVxbPWOGDEKmXPbqza697Aiw7k9hKZLxSvVLXDhtltFatgr8yUAcqZqjbeEeH/AFGwPwvMfieLqbgqBmuMt8xIO4sALyHw/AplOoREXNUf8KjUKL9bAmQFrmuxCKaWHH3RcPV1sDVb3jf8N7d79PJycvLas3idV/TvP6PRpxsUW1ETMx536WMDgKaG9KkQLk5mYkLfcAX+lpdx3EaaD/FrhfK6j5A3MyXE6lDCUg+JIAIsqC+Ym2iqBqT6bTmFDgRxVVnVXpUC1wruXa3mep/TqTOWeJaY+TPbUT69ummbrt00jevfqGcr8YwDtYK+IfooV6gJ9GsvxmB5j9pRrU660hRBIKqCtwV7hfCtxpoTNu4ZhKVFCKKqqgXaq2gNtzf7w89BNW4o38XWBTM1NN6jaBz+QdF87azTh/Vl1SJ6dTvc/wBvCnJ7U+qe/puBxjFb0QBmAJqP566DdvoPWQEQM+7Vn7v7q+i9Pp8ZbwPDK1Wwd2CAABV8IsNANNZunB+CKgAC2m2LgRE957f97VvzIiO0d1/l/h2QXOrHVj3m2U1sJFweHsJNnq0pFI1Hh5OS83tuSInsuzIiICah9olK9BGt7rkE9gw/7CbfMRzLgzVw1RFF2IBUdypBt9DA5AXlOaW8SCrEEEWNiDoQeoN5bFSWQxnHF90/CY9RpMlxY3X4zGodJCVRiDKS0D0ygiL3jb9yYAjvp+sqVb2ABJOygXJ17fvMnwfgNbEsMilV6uw/QGdP5b5MpUAGIzP1Y6mBpnL3JL1rPWGVOiDr/N3nUeFcGp0VCogAHlMjSogaAS+FgKazmHMmGanxGoW92pldCdiBYNb0N51CQOKcMo4hQtVQ1jdTsyna6kaj9+syzY/kpNXRxs/w5Is1DHcQVcMKdwC1Ulx1KomZR6FgnyMjLjzSw5emqu65SqtexYd8up1N9O09505fCUfa03ZvZ7hrE5erXFtja+neY3hOIDqy397UeVxqPUGeNyaZMWKkTHiY/Z7PH+LNW/TPmdsa2HZ2OKx1XM35jYAdFUDQD8o1PUnaZTCU2r6kZKC7LsXt+Lsvl8+0xmE4BXaqGrtmynw290eYHft29ZnsSdBSTYaN/T+syt1Z8kVidz7n1Efl+bS2SuHF9Ma+0IePrmocigZB0tobbafoJM4ZwkkgsJk+FcJ2JE2rB8PAG09rDhrjrFaxqIeHky2tbcz3QsBw0ADSZyhhwJcp0QJcm8Qwm0yT2IkqkREBERA8JkHFObGTHkKuJI5lzPwJ/aPVQk5tWQ6i/wCJe19LiagxINrWPUTs+LogzTOYOXg93QWby6wNCxr3WY6m2ky2NwrLmVhYj9phqW8C6TKCO8qJ6fLqT6TZeX+T61chnBRP9x/pA1/DYZ6jZEUu3YbD1PSb/wAt8hXs+I8R3C/dE3LgfLdKgoCIB521Mz6JbaBFwPDkQAKoAHaTFWVhZUqwPAJWonoWVWgWnEjVntJdZgqlmIAAJJOwA1JPaaDxX7R8AEvRrLUY3tdXULbq2YAnfQdfKRMpiNzpO5k4wmHpM76ixAT8ZP3bfrOR4HG4jNdVCZiWC5dEW+gH99pmm4gmKcPUrIxJ8CM6+Eea3svp+sztLBJTGlmdtvPsfSebyuR9UUiu5l7fEwUw0+S1u/2hZw2KrFArN4jq2UAWB2Gkz3COHbEiUcM4USczDU6zb8BgwBtOjBhikeHDyM/VaZXcDhQBMiq2hVtPZ1OKZ29iIhBERAREQEREChpFqLJhEtMkkY2pTkSth79Jl2SW2pQhpHHuXRUUkCzdDOapyxjDVyLQO9s5IyAd+5nf/YCephV7QlonLXI1OlZ3Gd+pb9pu+HwqqLASUtMStVgW1WXAs9yyoJCFIErAE9yiVWkJUie2lUhcTxyUKT1qhsiKWY+QGwHUnYDzgc8+2fmf2NAYOm1nri9Qj7tG9iP8xBHoGnByZneZOJ1cVXqYmsGXOboCCAqAlVVb9Baxt1v3mLyAhQLXPQf3vAq4bh87ajwrqfPsJ27kPhjvRV3G98l98n3b/W3lac24Jwos6oo0J8X7/wBJ37gGFKU1BGwA+QiY2tE6SKGBAtJ6raVRCJnb2IiEEREBERAREQEREBERAoKykpLsQLGWVBJctEnYoyz1VlcSB5aBPYgIiICcX+2fmol1wVJtFKvX7Ft0pm3YWY+q9p2icg5/5Gq1MU2JoUkdH1qIbBi+2ZSe+h33HnA5hS5irLVp1jlZqSqlPMLqgS+Xwm4945vWTOEYl3puuRSajqS7eJ2IzEgMRoLtc27DtGL5crIGD4dlYHwnxAW7GxI+M23kHgDVHUsuVV6RqE7luPI/LYVFdhrOgooAsJawtAIoUSRCCIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICUkAyqIESvgEbdRPMHw9KfuqB6CTIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgf/2Q==" alt="Olive drab green insulated bottle with flared screw lid and flat top." class="w-full h-full object-center object-cover group-hover:opacity-75">
        </div>
        <h3 class="mt-4 text-sm text-gray-700">Servo mg996r</h3>
      </a>

      <a href="#" class="group">
        <div class="w-full aspect-w-1 aspect-h-1 bg-gray-200 rounded-lg overflow-hidden xl:aspect-w-7 xl:aspect-h-8">
          <img src="https://http2.mlstatic.com/D_NQ_NP_640191-MLA32819282338_112019-O.jpg" alt="Person using a pen to cross a task off a productivity paper card." class="w-full h-full object-center object-cover group-hover:opacity-75">
        </div>
        <h3 class="mt-4 text-sm text-gray-700">Servo sg90</h3>
      </a>

      <a href="#" class="group">
        <div class="w-full aspect-w-1 aspect-h-1 bg-gray-200 rounded-lg overflow-hidden xl:aspect-w-7 xl:aspect-h-8">
          <img src="https://d3ugyf2ht6aenh.cloudfront.net/stores/648/727/products/lm2596-51-d8ac439043b7d636b715287637988900-1024-1024.jpg" alt="Hand holding black machined steel mechanical pencil with brass tip and top." class="w-full h-full object-center object-cover group-hover:opacity-75">
        </div>
        <h3 class="mt-4 text-sm text-gray-700">Step down lm2596</h3>
      </a>
      <a href="#" class="group">
        <div class="w-full aspect-w-1 aspect-h-1 bg-gray-200 rounded-lg overflow-hidden xl:aspect-w-7 xl:aspect-h-8">
          <img src="https://www.todomicro.com.ar/7424-large_default/adaptador-de-niveles-logicos-5v-a-33v-8-canales.jpg" alt="Hand holding black machined steel mechanical pencil with brass tip and top." class="w-full h-full object-center object-cover group-hover:opacity-75">
        </div>
        <h3 class="mt-4 text-sm text-gray-700">conversor de niveles lógicos 3.3/5v</h3>
      </a>

      <!-- More products... -->
    </div>
  </div>
</div>

  </div>

</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
