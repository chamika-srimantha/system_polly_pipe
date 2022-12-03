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
    public partial class Form3 : Form
    {
       
        
        public Form3()
        {
            InitializeComponent();
        }

        SqlConnection con = new SqlConnection("Data Source=LAPTOP-79CKPI4B;Initial Catalog=Polly_Pipe_db;Integrated Security=True");

        private void Form3_Load(object sender, EventArgs e)
        {
            LoadAllRecords();
        }
        
        private void btn_insert_Click(object sender, EventArgs e)
        {
            if (txt_employeeID.Text == "" || txt_employeeName.Text == "" || txt_employeeType.Text == "" || txt_employeecontactNo.Text == "" || txt_employeeSalary.Text == "" || txt_employeeAddress.Text == "")
            {
                MessageBox.Show("Missing Information");
            }
            else
            {
                try
                {
                    con.Open();
                    SqlCommand com = new SqlCommand("exec dbo.SP_Employee_Insert '" + int.Parse(txt_employeeID.Text) + "', '" + txt_employeeName.Text + "', '" + txt_employeeType.Text + "','" + txt_employeecontactNo.Text + "','" + txt_employeeSalary.Text + "','" + txt_employeeAddress.Text + "'", con);
                    com.ExecuteNonQuery();
                    con.Close();
                    LoadAllRecords();
                    MessageBox.Show("Successfully Inserted");
                }
                catch ( Exception Myex)
                {
                    MessageBox.Show(Myex.Message);
                }
            }
        }

        void LoadAllRecords()
        {
            SqlCommand com = new SqlCommand("exec dbo.SP_Employee_View", con);
            SqlDataAdapter da = new SqlDataAdapter(com);
            DataTable dt = new DataTable();
            da.Fill(dt);
            dataGridView1.DataSource = dt;
        }
        
        private void btn_home_Click(object sender, EventArgs e)
        {
            Form2 page = new Form2();
            page.Show();
            this.Hide();
        }

        private void btn_delete_Click(object sender, EventArgs e)
        {
            if (txt_employeeID.Text == "")
            {
                MessageBox.Show("Missing Information");
            }
            else
            {
                try
                {

                    con.Open();
                    SqlCommand com = new SqlCommand("exec dbo.SP_Employee_Delete '" + int.Parse(txt_employeeID.Text) + "'", con);
                    com.ExecuteNonQuery();
                    con.Close();
                    LoadAllRecords();
                    MessageBox.Show("Successfully Deleted");
                }
                catch
                {
                    MessageBox.Show("");
                }
            }
        }

        private void btn_update_Click(object sender, EventArgs e)
        {
            if (txt_employeeID.Text == "" || txt_employeeName.Text == "" || txt_employeeType.Text == "" || txt_employeecontactNo.Text == "" || txt_employeeSalary.Text == "" || txt_employeeAddress.Text == "")
            {
                MessageBox.Show("Missing Information");
            }
            else
            {
                try
                {
            con.Open();
            SqlCommand com = new SqlCommand("exec dbo.SP_Employee_Update '" + int.Parse(txt_employeeID.Text) + "', '" + txt_employeeName.Text + "', '" + txt_employeeType.Text + "','" + txt_employeecontactNo.Text + "','" + txt_employeeSalary.Text + "','" + txt_employeeAddress.Text + "'", con);
            com.ExecuteNonQuery();
            con.Close();
            LoadAllRecords();
            MessageBox.Show("Successfully Updated");
                }
                catch
                {
                    MessageBox.Show("");
                }
            }
        }


        private void btn_search_Click(object sender, EventArgs e)
        {
            using (DataTable dt = new DataTable("employee_form"))
            {
                using (SqlCommand cmd = new SqlCommand("Select * from employee_form where emp_id=@emp_id or emp_name like @emp_name", con))
                {
                    cmd.Parameters.AddWithValue("emp_id", txt_id.Text);
                    cmd.Parameters.AddWithValue("emp_name", string.Format("%{0}%", txt_id.Text));
                    SqlDataAdapter adapter = new SqlDataAdapter(cmd);
                    adapter.Fill(dt);
                    dataGridView1.DataSource = dt;

                }
            }              
        }

        private void btn_exit_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        private void btn_save_Click(object sender, EventArgs e)
        {
            txt_employeeID.Clear();
            txt_employeeName.Clear();
            txt_employeeType.Clear();
            txt_employeecontactNo.Clear();
            txt_employeeSalary.Clear();
            txt_employeeAddress.Clear();
        }
    }
}
