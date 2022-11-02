# Programa-tipo-Aplicacion
Este programa sirve para crear un Usuario y contraseña poder entrar con este a un segundo meno y una  vez ya en este poder editar tu nombre , usuario y contraseña, aparte de esto esta la posibilidad de que agregues tu platillo y película favorita   


using System;


using System.Net.NetworkInformation;


namespace Programa

{

    class Program
    
    {
    
        struct Menu
        
        {
        
            public string nombre;
            public string usuario;
            public string contra;
            public string pelicula;
            public string calif;
            public string peli;
            public string cal;
            public string platillo;
            public string cali;
            public string tipo;

        }




        static void Main(string[] args)
        {
            Menu p = new Menu();

            bool correrPrograma = true;
            while (correrPrograma == true)
            {
                ImprimirMenu();
                int opcion = Convert.ToInt32(Console.ReadLine());
                switch (opcion)
                {
                    case 1:
                        p = Sordo();

                        LimpiarConsola();
                        break;

                    case 2:
                        p = Ver(ref p);
                        LimpiarConsola();
                        break;



                    case 3:
                        correrPrograma = false;
                        break;

                    default:
                        Console.Write("Opcion invalida :( ");
                        LimpiarConsola();
                        break;

                }
            }
        }
        static void LimpiarConsola()
        {
            Console.Write("Presione Enter para continuar...");
            Console.ReadLine();
            Console.Clear();
        }
        static void ImprimirMenu()
        {
            Console.WriteLine("Menu");
            Console.WriteLine("-----------------------");
            Console.WriteLine("1 Alta de Usuario");
            Console.WriteLine("2 Acceder al Sistema");
            Console.WriteLine("3 Salir");
            Console.WriteLine("----------------------");

            Console.Write("Elegir opcion: ");

        }
        static Menu Sordo()
        {
            Menu autoTemporal = new Menu();


            Console.Write("Ingrese su nombre : ");
            autoTemporal.nombre = Console.ReadLine();
            Console.Write("Ingrese su nombre de usuario :");
            autoTemporal.usuario = Console.ReadLine();
            Console.Write("Ingrese una contraseña: ");
            autoTemporal.contra = Console.ReadLine();
            return autoTemporal;
        }
        static Menu Ver(ref Menu p)
        {




            Console.WriteLine("Ingrese su Usuario");
            string confirmación = Console.ReadLine();

            if (confirmación == p.usuario)
            {


                Console.WriteLine("Ingrese su contraseña con el 0 incluido: ");
                string confirmación2 = Console.ReadLine();
                if (confirmación2 == p.contra)
                {


                    bool correrPrograma = true;
                    while (correrPrograma == true)
                    {
                        ImprimirMenu();
                        int opcion = Convert.ToInt32(Console.ReadLine());
                        switch (opcion)
                        {
                            case 1:
                                Informacion(ref p);
                                LimpiarConsola();
                                break;

                            case 2:
                                p = Editar(ref p);
                                LimpiarConsola();
                                break;

                            case 3:
                                Plato(ref p);
                                LimpiarConsola();
                                break;

                            case 4:
                                p = Edit(ref p);
                                LimpiarConsola();
                                break;

                            case 5:
                                Peli(ref p);
                                LimpiarConsola();
                                break;

                            case 6:
                                Efit(ref p);
                                LimpiarConsola();
                                break;


                            case 7:
                                correrPrograma = false;
                                break;

                                return p;

                            default:
                                Console.Write("Opcion invalida :( ");
                                LimpiarConsola();
                                break;

                        }
                        static void ImprimirMenu()
                        {
                            Console.WriteLine("ACCESO DE SISTEMA");
                            Console.WriteLine("-----------------------");
                            Console.WriteLine("1 Ver Informacion del Usuario");
                            Console.WriteLine("2 Editar Informacion de Usuario");
                            Console.WriteLine("3 Editar  su platillo favorito ");
                            Console.WriteLine("4 Ver su  platillo Favorito");
                            Console.WriteLine("5 Ingresar Pelicula Favorita ");
                            Console.WriteLine("6 Ver Pelicula Favorita ");
                            Console.WriteLine("7 Salir");
                            Console.WriteLine("----------------------");

                            Console.Write("Elegir opcion: ");

                        }

                        static void Informacion(ref Menu p)
                        {

                            Console.WriteLine($"El nombre es:{p.nombre}");
                            Console.WriteLine($"El usuario es :{p.usuario}");
                            Console.WriteLine($"La contraseña es : {p.contra}");


                        }

                        static Menu Editar(ref Menu p)
                        {



                            Console.Write("Ingrese su nuevo  nombre : ");
                            p.nombre = Console.ReadLine();
                            Console.Write("Ingrese su nuevo nombre de usuario : ");
                            p.usuario = Console.ReadLine();
                            Console.Write("Ingrese su nueva contraseña: ");
                            p.contra = Console.ReadLine();
                            return p;




                        }

                        static Menu Plato(ref Menu p)
                        {



                            Console.Write("Ingrese su Platillo : ");
                            p.platillo = Console.ReadLine();

                            Console.Write("Ingrese el tipo de platillo : ");
                            p.tipo = Console.ReadLine();
                            Console.Write("Ingrese la calificacion dek platillo  : ");
                            p.cali = Console.ReadLine();
                            return p;
                        }

                        static Menu Edit(ref Menu p)
                        {
                            Console.WriteLine($"El platillo es:{p.platillo}");
                            Console.WriteLine($"El platillo es:{p.tipo}");
                            Console.WriteLine($"La calificacion es :{p.cali}");

                            return p;

                        }
                        static Menu Peli(ref Menu p)
                        {



                            Console.Write("Ingrese el nombre de la pelicula  : ");
                            p.peli = Console.ReadLine();
                            Console.Write("Ingrese la calificacion de la pelicula  : ");
                            p.cal = Console.ReadLine();
                            return p;
                        }
                        static Menu Efit(ref Menu p)
                        {
                            Console.WriteLine($"El platillo es:{p.peli}");
                            Console.WriteLine($"La calificacion es :{p.cal}");



                            return p;
                        }


                    }

                }


                else
                {
                    Console.WriteLine("Contraseña incorrecta intente de nuevo ");
                }






            }
            else
            {
                Console.WriteLine("Usuario no encontrado intente de nuevo");
            }

            return p;
        }
    }

}


