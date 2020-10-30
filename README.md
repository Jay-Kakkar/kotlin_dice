package com.example.diceroller

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.widget.Button
import android.widget.ImageView
import android.widget.TextView
import android.widget.Toast
import kotlin.random.Random
import kotlin.random.Random.Default.nextInt

class MainActivity : AppCompatActivity() {
    lateinit var imageView: ImageView;
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val diceRollButton: Button = findViewById(R.id.button);
        diceRollButton.setText("Let's Roll");
        diceRollButton.setOnClickListener {
            rollButton();
        }
        imageView=findViewById(R.id.image_dice)
    }

    private fun rollButton() {
        val randomInt = Random.nextInt(1, 7)


        val drawableDice = when (randomInt) {
            1 -> R.drawable.dice_1
            2 -> R.drawable.dice_2
            3 -> R.drawable.dice_3
            4 -> R.drawable.dice_4
            5 -> R.drawable.dice_5
            6 -> R.drawable.dice_6
            else -> R.drawable.empty_dice
        }
        imageView.setImageResource(drawableDice)
    }
}
