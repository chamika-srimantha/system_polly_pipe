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
    public partial class Register : Form
    {
        public Register()
        {
            InitializeComponent();
        }

        SqlConnection con = new SqlConnection("Data Source=LAPTOP-79CKPI4B;Initial Catalog=Polly_Pipe_db;Integrated Security=True");

        private void btn_register_Click(object sender, EventArgs e)
        {
            con.Open();
            SqlCommand com = new SqlCommand("exec dbo.SP_Register '" + txt_username.Text + "', '" + txt_password.Text + "', '" + int.Parse(txt_age.Text) + "'", con);
            com.ExecuteNonQuery();
            con.Close();          
            MessageBox.Show("Successfully Registered");
            LoadAllRecords();
            this.Hide();
            Form1 page = new Form1();
            page.Show();
        }

        void LoadAllRecords()
        {
            SqlCommand com = new SqlCommand("exec dbo.SP_Employee_View", con);
            SqlDataAdapter da = new SqlDataAdapter(com);
            DataTable dt = new DataTable();
            da.Fill(dt);
            
        }

        private void Register_Load(object sender, EventArgs e)
        {
            LoadAllRecords();
        }

        private void btn_login_Click(object sender, EventArgs e)
        {
            this.Hide();
            Form1 page = new Form1();
            page.Show();
        }

        private void btn_exit_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }
    }
}
