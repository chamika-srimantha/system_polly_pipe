using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace db_assignment
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
            txt_password.PasswordChar = '*';
            txt_password.MaxLength = 20;
        }

        private void txt_password_TextChanged(object sender, EventArgs e)
        {

        }

        private void btn_login_Click(object sender, EventArgs e)
        {
            String username = txt_username.Text;
            String password = txt_password.Text;

            if (username == "Chamika" && password == "Chamika@123")
            {
                //if username and password correct
                MessageBox.Show(" Login Success ","LOG IN",MessageBoxButtons.OK,MessageBoxIcon.Information);

                //if user login correct change the page 
                Form2 page = new Form2();
                page.Show();
                this.Hide();
            }
            else
            { 
            //if user login incorrect
                MessageBox.Show("  Login not Success  ","LOG IN", MessageBoxButtons.OK,MessageBoxIcon.Error);
            }
        }

        private void btn_exit_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }
    }
}
