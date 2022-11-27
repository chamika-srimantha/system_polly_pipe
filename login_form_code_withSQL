using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Data.SqlClient;
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
            SqlConnection con = new SqlConnection(@"Data Source=LAPTOP-79CKPI4B;Initial Catalog=Polly_Pipe_db;Integrated Security=True");
            SqlDataAdapter sda = new SqlDataAdapter("SELECT COUNT(*) FROM login_form WHERE username ='" + txt_username.Text + "' AND password='" + txt_password.Text + "'", con);

            DataTable dt = new DataTable();
            sda.Fill(dt);
            if (dt.Rows[0][0].ToString() == "1")
            {
                MessageBox.Show(" Login Success ", "LOG IN", MessageBoxButtons.OK, MessageBoxIcon.Information);

                this.Hide();
                Form2 page = new Form2();
                page.Show();
            }
            else
            {
                MessageBox.Show("Login not Success  ", "LOG IN", MessageBoxButtons.OK, MessageBoxIcon.Error);
            }
        }

        private void btn_exit_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }
    }
}
