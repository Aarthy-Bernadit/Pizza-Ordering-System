# Pizza-Ordering-System
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace pizza
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }
        public void CalculatePrice()
        {
            double PriceSize = 0.00;
            double PriceEachTopping, BWings, Bread,
                SodaCan, Soda20, Soda2L, OJ, Water, PriceToppings, TotalOrder;
            int Pepperoni, Sausage, ExtraCheese, Onions, Olives;

            // Get the price of pizza depending on the selected size
            if (rdoSmall.Checked == true)
                PriceSize = double.Parse(textBox1.Text);
            if (rdoMedium.Checked == true)
                PriceSize = double.Parse(textBox2.Text);
            if (rdoLarge.Checked == true)
                PriceSize = double.Parse(textBox3.Text);

            // Get the price of a topping if it was selected
            if (chkPepperoni.Checked == true)
                Pepperoni = 1;
            else
                Pepperoni = 0;

            if (chkSausage.Checked == true)
                Sausage = 1;
            else
                Sausage = 0;

            if (chkExtraCheese.Checked == true)
                ExtraCheese = 1;
            else
                ExtraCheese = 0;

            if (chkOnions.Checked == true)
                Onions = 1;
            else
                Onions = 0;

            if (chkOlives.Checked == true)
                Olives = 1;
            else
                Olives = 0;

            PriceEachTopping = double.Parse(txtEachTopping.Text);
            PriceToppings = (Pepperoni + Sausage + ExtraCheese + Onions + Olives) * PriceEachTopping;

            // Calculate the price of the side dishes
            // depending on the quantity entered
            BWings = double.Parse(txtTotalWings.Text);
            Bread = double.Parse(txtTotalBread.Text);

            // Calculate the price of the drink(s)
            SodaCan = double.Parse(txtTotalCan.Text);
            Soda20 = double.Parse(txtTotalSoda20.Text);
            Soda2L = double.Parse(txtTotalSoda2L.Text);
            OJ = double.Parse(txtTotalOJ.Text);
            Water = double.Parse(txtTotalWater.Text);

            TotalOrder = PriceSize + PriceToppings + BWings + Bread +
                SodaCan + Soda20 + Soda2L + OJ + Water;
          //  txtTotalPrice.Text = TotalOrder.ToString("C");
        }
        private void rdoSmall_CheckedChanged(object sender, System.EventArgs e)
        {
            CalculatePrice();
        }

        private void rdoMedium_CheckedChanged(object sender, System.EventArgs e)
        {
            CalculatePrice();
        }

        private void rdoLarge_CheckedChanged(object sender, System.EventArgs e)
        {
            CalculatePrice();
        }

        private void chkPepperoni_CheckedChanged(object sender, System.EventArgs e)
        {
            CalculatePrice();
        }

        private void chkSausage_CheckedChanged(object sender, System.EventArgs e)
        {
            CalculatePrice();
        }

        private void chkExtraCheese_CheckedChanged(object sender, System.EventArgs e)
        {
            CalculatePrice();
        }

        private void chkOlives_CheckedChanged(object sender, System.EventArgs e)
        {
            CalculatePrice();
        }

        private void chkOnions_CheckedChanged(object sender, System.EventArgs e)
        {
            CalculatePrice();
        }

        private void txtQtyBread_Leave(object sender, System.EventArgs e)
        {
            int Qty;
            double Price, Total;

            if (txtQtyBread.Text == "")
                Qty = 0;
            else
                Qty = Int32.Parse(txtQtyBread.Text);

            Price = double.Parse(txtPriceBread.Text);

            Total = Qty * Price;
            txtTotalBread.Text = Total.ToString("F");

            CalculatePrice();
        }

        private void txtQtyWings_Leave(object sender, System.EventArgs e)
        {
            int Qty;
            double Price, Total;

            if (txtQtyBread.Text == "")
                Qty = 0;
            else
                Qty = Int32.Parse(txtQtyBread.Text);

            Price = double.Parse(txtPriceWings.Text);

            Total = Qty * Price;
            txtTotalWings.Text = Total.ToString("F");

            CalculatePrice();
        }

        private void txtQtyCan_Leave(object sender, System.EventArgs e)
        {
            int Qty;
            double Price, Total;

            if (txtQtyCan.Text == "")
                Qty = 0;
            else
                Qty = Int32.Parse(txtQtyCan.Text);

            Price = double.Parse(txtPriceCan.Text);

            Total = Qty * Price;
            txtTotalCan.Text = Total.ToString("F");

            CalculatePrice();
        }

        private void txtQtySoda20_Leave(object sender, System.EventArgs e)
        {
            int Qty;
            double Price, Total;

            if (txtQtySoda20.Text == "")
                Qty = 0;
            else
                Qty = Int32.Parse(txtQtySoda20.Text);

            Price = double.Parse(txtPriceSoda20.Text);

            Total = Qty * Price;
            txtTotalSoda20.Text = Total.ToString("F");

            CalculatePrice();
        }

        private void txtQtySoda2L_Leave(object sender, System.EventArgs e)
        {
            int Qty;
            double Price, Total;

            if (txtQtySoda2L.Text == "")
                Qty = 0;
            else
                Qty = Int32.Parse(txtQtySoda2L.Text);

            Price = double.Parse(txtPriceSoda2L.Text);

            Total = Qty * Price;
            txtTotalSoda2L.Text = Total.ToString("F");

            CalculatePrice();
        }

        private void txtQtyOJ_Leave(object sender, System.EventArgs e)
        {
            int Qty;
            double Price, Total;

            if (txtQtyOJ.Text == "")
                Qty = 0;
            else
                Qty = Int32.Parse(txtQtyOJ.Text);

            Price = double.Parse(txtPriceOJ.Text);

            Total = Qty * Price;
            txtTotalOJ.Text = Total.ToString("F");

            CalculatePrice();
        }

        private void txtQtyWater_Leave(object sender, System.EventArgs e)
        {
            int Qty;
            double Price, Total;

            if (txtQtyWater.Text == "")
                Qty = 0;
            else
                Qty = Int32.Parse(txtQtyWater.Text);

            Price = double.Parse(txtPriceWater.Text);

            Total = Qty * Price;
            txtTotalWater.Text = Total.ToString("F");

            CalculatePrice();
        }
       private void button1_Click(object sender, System.EventArgs e)
        {
           Close();
       }

       
    }
}
