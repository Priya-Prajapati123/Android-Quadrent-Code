# Android-Quadrent-Code
package com.example.quadrent

import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.compose.foundation.background
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.fillMaxWidth
import androidx.compose.foundation.layout.padding
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.res.stringResource
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.text.font.FontWeight.Companion.Bold
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.quadrent.ui.theme.QuadrentTheme

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            QuadrentTheme {
                Surface(
                    modifier = Modifier.fillMaxSize(),
                    color = MaterialTheme.colorScheme.background
                ) {
                    Quadrent()
                }
            }
        }
    }
}

    @Composable
fun Quadrent() {
    Column(Modifier.fillMaxWidth()) {
        Row(Modifier.weight(1f)) {
            Greeting(
                title = stringResource(R.string.title1),
                description = stringResource(R.string.description1),
                backgroundColor = Color(0xFFEADDFF),
                modifier = Modifier.weight(1f)
            )
            Greeting(
                title = stringResource(R.string.title2),
                description = stringResource(R.string.description2),
                backgroundColor = Color(0xFFD0BCFF),
                modifier = Modifier.weight(1f)
                )
        }
        Row(Modifier.weight(1f)) {
            Greeting(
                title = stringResource(R.string.title3),
                description = stringResource(R.string.description3),
                backgroundColor = Color(0xFFB69DF8),
                modifier = Modifier.weight(1f)
            )
            Greeting(
                title = stringResource(R.string.title4),
                description = stringResource(R.string.description4),
                backgroundColor = Color(0xFFEADDFF),
                modifier = Modifier.weight(1f)
            )
        }
    }
}
@Composable
fun Greeting(title: String, description: String, backgroundColor:Color, modifier: Modifier) {
    Column(
        modifier = modifier
            .fillMaxSize()
            .background(backgroundColor)
            .padding(16.dp),
        verticalArrangement = Arrangement.Center,
        horizontalAlignment = Alignment.CenterHorizontally
    ) {
        Text(
            text = title,
            fontWeight = FontWeight.Bold
        )
        Text(
            text = description,
            textAlign = TextAlign.Justify
        )
    }
}
    @Preview(showBackground = true)
    @Composable
    fun GreetingPreview() {
        QuadrentTheme {
            Quadrent(
            )
        }
    }
