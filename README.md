# Calculadora
Repositorio de la aplicación "Calculadora" para el curso de Aplicaciones Móviles

--------------------------------------------------- Aplicación móvil: Calculadora -------------------------------------------

------ Actividad Principal ------- 

package com.example.admin.aplicacion;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.Menu;
import android.view.MenuItem;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    private static final String SUMA = "suma";
    private static final String RESTA = "resta";
    private static final String MULTIPLICACION = "multiplicacion";
    private static final String DIVISION = "division";

    private Integer num1;
    private Integer num2;

    private TextView txtOperacion;
    private EditText campoTxtResultado;
    private Button btnIgual, btnSumar, btnRestar, btnMultiplicar, btnDividir, btnBorrar, btnReiniciar;
    private Button btnCero, btnUno, btnDos, btnTres, btnCuatro, btnCinco, btnSeis, btnSiete, btnOcho, btnNueve;

    private String tipoOperacion;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        txtOperacion = (TextView) findViewById(R.id.textView2);
        campoTxtResultado = (EditText) findViewById(R.id.editText);
        btnIgual = (Button) findViewById(R.id.igual);
        btnIgual.setOnClickListener(new View.OnClickListener()
        {
            public void onClick(View v)
            {
                if(num1 != null)
                    resultado(num1, num2);
            }
        });

        btnSumar = (Button) findViewById(R.id.sumar);
        btnSumar.setOnClickListener(new View.OnClickListener()
        {
            public void onClick(View v)
            {
                tipoOperacion = SUMA;

                if(num1 == null)
                    num1 = Integer.parseInt(String.valueOf(campoTxtResultado.getText()));
                else
                {
                    num2 = Integer.parseInt(String.valueOf(campoTxtResultado.getText()));

                    int suma = num1+num2;
                    campoTxtResultado.setText("" + (suma));
                    txtOperacion.setText(num1 + " + " + num2 + " = " + suma);
                }
            }
        });

        btnRestar = (Button) findViewById(R.id.restar);
        btnRestar.setOnClickListener(new View.OnClickListener()
        {
            public void onClick(View v)
            {
                tipoOperacion = RESTA;

                if(num1 == null)
                    num1 = Integer.parseInt(String.valueOf(campoTxtResultado.getText()));
                else
                {
                    num2 = Integer.parseInt(String.valueOf(campoTxtResultado.getText()));

                    int resta = num1-num2;
                    campoTxtResultado.setText("" + (resta));
                    txtOperacion.setText(num1 + " - " + num2 + " = " + resta);
                }
            }
        });

        btnMultiplicar = (Button) findViewById(R.id.multiplicar);
        btnMultiplicar.setOnClickListener(new View.OnClickListener()
        {
            public void onClick(View v)
            {
                tipoOperacion = MULTIPLICACION;

                if(num1 == null)
                    num1 = Integer.parseInt(String.valueOf(campoTxtResultado.getText()));
                else
                {
                    num2 = Integer.parseInt(String.valueOf(campoTxtResultado.getText()));

                    int multiplicacion = num1*num2;
                    campoTxtResultado.setText("" + (multiplicacion));
                    txtOperacion.setText(num1 + " * " + num2 + " = " + multiplicacion);
                }
            }
        });

        btnDividir = (Button) findViewById(R.id.dividir);
        btnDividir.setOnClickListener(new View.OnClickListener()
        {
            public void onClick(View v)
            {
                tipoOperacion = DIVISION;

                if(num1 == null)
                    num1 = Integer.parseInt(String.valueOf(campoTxtResultado.getText()));
                else
                {
                    num2 = Integer.parseInt(String.valueOf(campoTxtResultado.getText()));

                    int division = num1/num2;
                    campoTxtResultado.setText("" + (division));
                    txtOperacion.setText(num1 + " / " + num2 + " = " + division);
                }
            }
        });

        btnBorrar = (Button) findViewById(R.id.borrar);
        btnBorrar.setOnClickListener(new View.OnClickListener()
        {
            public void onClick(View v)
            {
               campoTxtResultado.setText("");
            }
        });

        btnReiniciar = (Button) findViewById(R.id.reiniciar);
        btnReiniciar.setOnClickListener(new View.OnClickListener()
        {
            public void onClick(View v)
            {
                campoTxtResultado.setText("");
                num1 = null;
                num2 = null;
            }
        });

        btnCero = (Button) findViewById(R.id.cero);
        btnCero.setOnClickListener(new View.OnClickListener()
        {
            public void onClick(View v)
            {
                if(cuadroVacio(v) == true)
                    campoTxtResultado.setText("0");
                else
                    campoTxtResultado.setText(campoTxtResultado.getText() + "0");
            }
        });

        btnUno = (Button) findViewById(R.id.uno);
        btnUno.setOnClickListener(new View.OnClickListener()
        {
            public void onClick(View v)
            {
                if(cuadroVacio(v) == true)
                    campoTxtResultado.setText("1");
                else
                    campoTxtResultado.setText(campoTxtResultado.getText() + "1");
            }
        });

        btnDos = (Button) findViewById(R.id.dos);
        btnDos.setOnClickListener(new View.OnClickListener()
        {
            public void onClick(View v)
            {
                if(cuadroVacio(v) == true)
                    campoTxtResultado.setText("2");
                else
                    campoTxtResultado.setText(campoTxtResultado.getText() + "2");
            }
        });

        btnTres = (Button) findViewById(R.id.tres);
        btnTres.setOnClickListener(new View.OnClickListener()
        {
            public void onClick(View v)
            {
                if(cuadroVacio(v) == true)
                    campoTxtResultado.setText("3");
                else
                    campoTxtResultado.setText(campoTxtResultado.getText() + "3");
            }
        });

        btnCuatro = (Button) findViewById(R.id.cuatro);
        btnCuatro.setOnClickListener(new View.OnClickListener()
        {
            public void onClick(View v)
            {
                if(cuadroVacio(v) == true)
                    campoTxtResultado.setText("4");
                else
                    campoTxtResultado.setText(campoTxtResultado.getText() + "4");
            }
        });

        btnCinco = (Button) findViewById(R.id.cinco);
        btnCinco.setOnClickListener(new View.OnClickListener()
        {
            public void onClick(View v)
            {
                if(cuadroVacio(v) == true)
                    campoTxtResultado.setText("5");
                else
                    campoTxtResultado.setText(campoTxtResultado.getText() + "5");
            }
        });

        btnSeis = (Button) findViewById(R.id.seis);
        btnSeis.setOnClickListener(new View.OnClickListener()
        {
            public void onClick(View v)
            {
                if(cuadroVacio(v) == true)
                    campoTxtResultado.setText("6");
                else
                    campoTxtResultado.setText(campoTxtResultado.getText() + "6");
            }
        });

        btnSiete = (Button) findViewById(R.id.siete);
        btnSiete.setOnClickListener(new View.OnClickListener()
        {
            public void onClick(View v)
            {
                if(cuadroVacio(v) == true)
                    campoTxtResultado.setText("7");
                else
                    campoTxtResultado.setText(campoTxtResultado.getText() + "7");
            }
        });

        btnOcho = (Button) findViewById(R.id.ocho);
        btnOcho.setOnClickListener(new View.OnClickListener()
        {
            public void onClick(View v)
            {
                if(cuadroVacio(v) == true)
                    campoTxtResultado.setText("8");
                else
                    campoTxtResultado.setText(campoTxtResultado.getText() + "8");
            }
        });

        btnNueve = (Button) findViewById(R.id.nueve);
        btnNueve.setOnClickListener(new View.OnClickListener()
        {
            public void onClick(View v)
            {
                if(cuadroVacio(v) == true)
                    campoTxtResultado.setText("9");
                else
                    campoTxtResultado.setText(campoTxtResultado.getText() + "9");
            }
        });

    }

    @Override
    public boolean onCreateOptionsMenu(Menu menu) {
        // Inflate the menu; this adds items to the action bar if it is present.
        getMenuInflater().inflate(R.menu.menu_main, menu);
        return true;
    }

    @Override
    public boolean onOptionsItemSelected(MenuItem item) {
        // Handle action bar item clicks here. The action bar will
        // automatically handle clicks on the Home/Up button, so long
        // as you specify a parent activity in AndroidManifest.xml.
        int id = item.getItemId();

        //noinspection SimplifiableIfStatement
        if (id == R.id.action_settings) {
            return true;
        }

        return super.onOptionsItemSelected(item);
    }

    public boolean cuadroVacio(View view)
    {
        boolean vacio = false;

        if(campoTxtResultado.getText().equals(""))
            vacio = true;

        return vacio;
    }

    public void resultado(int val1, int val2)
    {

        switch (tipoOperacion)
        {
            case "suma":
                campoTxtResultado.setText("" + (val1+val2));
                break;
            case "resta":
                campoTxtResultado.setText("" + (val1-val2));
                break;
            case "multiplicacion":
                campoTxtResultado.setText("" + (val1*val2));
                break;
            case "division":
                campoTxtResultado.setText("" + (val1/val2));
        }
    }
